# flexera-api

index=max_database source=AwsAPI sourcetype="dynamodb-FlexeraUnusedResources_*" Table="FlexeraUnusedResources_Findings" earliest=-24h
| rename *.S as *, *.N as *, *.BOOL as *
| fieldsummary
| table field count distinct_count values
| sort field
