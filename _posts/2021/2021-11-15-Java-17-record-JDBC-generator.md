---
layout: post
status: publish
published: true
tags: Java 16, Java 17, records, JDBC, Code generator
title: "Generate Java 16/17+ records from JDBC resultset"
---
Since I couldn't surface anyone using Java records and generating them from a JDBC 
result set (as a lazy programmer I want to type as less code as I possibly can), here's a method that
just does that.

Caveats: some types are not generated correctly (e.g. arrays), but you can easily modify those types as you like.

```java
public static void resultSetToJavaRecordCodeGenerator(ResultSet rs) throws SQLException
{
	while (rs.next())
	{
		System.out.println("public record ChangeMyName(");
		var komma = "  ";
		for (int i = 1; i <= rs.getMetaData().getColumnCount(); i++)
		{
			var typeName = rs.getMetaData().getColumnClassName(i).replace("java.lang.", "");
			var fieldName = StringUtil.firstCharLowercase(rs.getMetaData().getColumnName(i));
			System.out.print("\t");
			System.out.print(komma);
			System.out.print(typeName);
			System.out.print(" ");
			System.out.println(fieldName);
			komma = ", ";
		}
		System.out.println(")");
		System.out.println("{");
		System.out.println("}");
		break;
	}
}

```

Given for example the columns returned from a SqlServer `RESTORE HEADERSONLY FROM DISK='/dumps/...'` you get this Java record:

```java
public record ChangeMyName(
	  String backupName
	, String backupDescription
	, Short backupType
	, java.sql.Timestamp expirationDate
	, Short compressed
	, Short position
	, Short deviceType
	, String userName
	, String serverName
	, String databaseName
	, Integer databaseVersion
	, java.sql.Timestamp databaseCreationDate
	, Long backupSize
	, java.math.BigDecimal firstLSN
	, java.math.BigDecimal lastLSN
	, java.math.BigDecimal checkpointLSN
	, java.math.BigDecimal databaseBackupLSN
	, java.sql.Timestamp backupStartDate
	, java.sql.Timestamp backupFinishDate
	, Short sortOrder
	, Short codePage
	, Integer unicodeLocaleId
	, Integer unicodeComparisonStyle
	, Short compatibilityLevel
	, Integer softwareVendorId
	, Integer softwareVersionMajor
	, Integer softwareVersionMinor
	, Integer softwareVersionBuild
	, String machineName
	, Integer flags
	, String bindingID
	, String recoveryForkID
	, String collation
	, String familyGUID
	, Boolean hasBulkLoggedData
	, Boolean isSnapshot
	, Boolean isReadOnly
	, Boolean isSingleUser
	, Boolean hasBackupChecksums
	, Boolean isDamaged
	, Boolean beginsLogChain
	, Boolean hasIncompleteMetaData
	, Boolean isForceOffline
	, Boolean isCopyOnly
	, String firstRecoveryForkID
	, java.math.BigDecimal forkPointLSN
	, String recoveryModel
	, java.math.BigDecimal differentialBaseLSN
	, String differentialBaseGUID
	, String backupTypeDescription
	, String backupSetGUID
	, Long compressedBackupSize
	, Short containment
	, String keyAlgorithm
	, [B encryptorThumbprint
	, String encryptorType
)
{
}
```
And yes, this will not compile because of the `[B encryptorThumbprint`, but that doesn't make this method anymore less useable.

Use this to your advantage!
