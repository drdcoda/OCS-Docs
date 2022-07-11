---
uid: pi-to-ocs-agents

---

# Agents
The Agents controller is used to manage agent interaction.

## `List All Agents`

<a id="opIdAgents_List All Agents"></a>

Get all `AgentDto` objects associated with the specified Namespace.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/agents
```

<h4>Parameters</h4>

`string tenantId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#tenantId<br/><br/>`string namespaceId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#namespaceId<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AgentDto](#schemaagentdto)[]|The requested collection of `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([AgentDto](#schemaagentdto)[])

```json
[
  {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": "string",
      "Name": "string",
      "Version": "string",
      "AFServerId": "string",
      "AFName": "string",
      "AFVersion": "string",
      "LastCommunicationTime": "2019-08-24T14:15:22Z",
      "Transfers": [
        {
          "Id": "string",
          "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
          "Description": "string",
          "Status": 0,
          "LatestStreamingRead": "2019-08-24T14:15:22Z",
          "OnPremTransferStatus": 0,
          "PIPointCount": 0,
          "Metrics": {
            "StreamingEventCountPerSecond": 0,
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "SuccessfulStreamEdits": 0,
            "FailedStreamEdits": 0,
            "PointEdits": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0,
            "FailedCreationPointIds": [
              0
            ],
            "SuccessfulStreamDeletions": 0,
            "FailedStreamDeletions": 0,
            "SuccessfulAssetDeletions": 0,
            "FailedAssetDeletions": 0,
            "SuccessfulAssetCreations": 0,
            "FailedAssetCreationsAndUpdates": 0,
            "IsModified": true,
            "SuccessfulAssetUpdates": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0,
          "TransferRevisionNumber": 0,
          "LastEditDate": "2019-08-24T14:15:22Z",
          "LastEditBy": "string",
          "AutoDeleteCloudObjects": true,
          "TotalPointsInTransfer": 0,
          "PIPointsWithHealthEvents": {
            "property1": {
              "MaxSeverity": 0,
              "EventId": 400001
            },
            "property2": {
              "MaxSeverity": 0,
              "EventId": 400001
            }
          },
          "AFElementsWithHealthEvents": {
            "property1": {
              "MaxSeverity": 0,
              "EventId": 400001
            },
            "property2": {
              "MaxSeverity": 0,
              "EventId": 400001
            }
          },
          "StreamCreationStatus": {
            "TransferId": "string",
            "Status": 0,
            "TotalPointStreamsExpected": 0,
            "VerifiedPointStreamsCreated": 0,
            "LastUpdateAttempt": "2019-08-24T14:15:22Z",
            "LastSuccessfulUpdate": "2019-08-24T14:15:22Z",
            "LastMessage": 0
          },
          "HistTransferProgress": {
            "TransferId": "string",
            "TotalArchives": 0,
            "CurrentArchive": 0,
            "TotalPointsInArchive": 0,
            "TransferredPointsForArchive": 0
          }
        }
      ],
      "AFIndexProgress": 0,
      "PIPointCacheProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0,
      "PointsIndexed": 0,
      "TotalPoints": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "SuccessfulStreamEdits": 0,
      "FailedStreamEdits": 0,
      "PointEdits": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0,
      "FailedCreationPointIds": [
        0
      ],
      "SuccessfulStreamDeletions": 0,
      "FailedStreamDeletions": 0,
      "SuccessfulAssetDeletions": 0,
      "FailedAssetDeletions": 0,
      "SuccessfulAssetCreations": 0,
      "FailedAssetCreationsAndUpdates": 0,
      "IsModified": true,
      "SuccessfulAssetUpdates": 0
    }
  }
]
```

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Capability Updates`

<a id="opIdAgents_Get Capability Updates"></a>

Handle Agent Capabilities Updates.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/capabilities
```

<h4>Parameters</h4>

`string tenantId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#tenantId<br/><br/>`string namespaceId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#namespaceId<br/><br/>`string agentId`
<br/>The Id of the specified on-prem agent.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A Dictionary object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post Capabilities`

<a id="opIdAgents_Post Capabilities"></a>

Handle Agent Capabilities Publishing.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/capabilities
```

<h4>Parameters</h4>

`string tenantId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#tenantId<br/><br/>`string namespaceId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#namespaceId<br/><br/>`string agentId`
<br/>The Id of the specified on-prem agent.<br/><br/>

<h4>Request Body</h4>

List of capabilities being published.<br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The capabilities published by the agent specified by `agentId` have been received and cached.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post Forwarded Logs`

<a id="opIdAgents_Post Forwarded Logs"></a>

Post log messages from the on-prem agent to be forwarded to Application Insights.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/logs
```

<h4>Parameters</h4>

`string tenantId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#tenantId<br/><br/>`string namespaceId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#namespaceId<br/><br/>`string agentId`
<br/>The Id of the specified on-prem agent.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Log messages from the specified on-prem `agentId` have been forwarded to Application Insights.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post`

<a id="opIdAgents_Post"></a>

Post Sync route for specified `agentId`.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#tenantId<br/><br/>`string namespaceId`
<br/>#https://raw.githubusercontent.com/osisoft/OCS-Docs/main/content/external-references/common.yaml#namespaceId<br/><br/>`string agentId`
<br/>The Id of the specified on-prem agent.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Sync route for specified `agentId` has been posted - OK.|
|202|None|Sync route for specified `agentId` has been posted - Accepted.|
|204|None|Sync route for specified `agentId` has been posted - No Content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### AgentDto

<a id="schemaagentdto"></a>
<a id="schema_AgentDto"></a>
<a id="tocSagentdto"></a>
<a id="tocsagentdto"></a>

Data Transfer Object for an Agent.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|LastCommTime|date-time|false|false|None|
|Version|string|false|true|None|
|Status|[AgentStatus](#schemaagentstatus)|false|false|None|
|Description|string|false|true|None|
|HostName|string|false|true|None|
|PISystem|[PISystemDto](#schemapisystemdto)|false|true|Data Transfer Object for a PI System.|
|Namespace|string|false|true|None|
|Region|string|false|true|None|
|IsDeprecated|boolean|false|false|None|
|TransferMetrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|Data Transfer Object for tracking metrics of a Transfer.|

```json
{
  "Id": "string",
  "LastCommTime": "2019-08-24T14:15:22Z",
  "Version": "string",
  "Status": 0,
  "Description": "string",
  "HostName": "string",
  "PISystem": {
    "ServerId": "string",
    "Name": "string",
    "Version": "string",
    "AFServerId": "string",
    "AFName": "string",
    "AFVersion": "string",
    "LastCommunicationTime": "2019-08-24T14:15:22Z",
    "Transfers": [
      {
        "Id": "string",
        "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
        "Description": "string",
        "Status": 0,
        "LatestStreamingRead": "2019-08-24T14:15:22Z",
        "OnPremTransferStatus": 0,
        "PIPointCount": 0,
        "Metrics": {
          "StreamingEventCountPerSecond": 0,
          "HistoricalEventCountPerSecond": 0,
          "SuccessfulCreations": 0,
          "FailedCreations": 0,
          "SuccessfulStreamEdits": 0,
          "FailedStreamEdits": 0,
          "PointEdits": 0,
          "TotalPoints": 0,
          "AssetsCreatedPerSecond": 0,
          "AssetsProcessedCount": 0,
          "TotalAssetsInTransfer": 0,
          "FailedCreationPointIds": [
            0
          ],
          "SuccessfulStreamDeletions": 0,
          "FailedStreamDeletions": 0,
          "SuccessfulAssetDeletions": 0,
          "FailedAssetDeletions": 0,
          "SuccessfulAssetCreations": 0,
          "FailedAssetCreationsAndUpdates": 0,
          "IsModified": true,
          "SuccessfulAssetUpdates": 0
        },
        "Name": "string",
        "MetadataPrivacy": 0,
        "TransferRevisionNumber": 0,
        "LastEditDate": "2019-08-24T14:15:22Z",
        "LastEditBy": "string",
        "AutoDeleteCloudObjects": true,
        "TotalPointsInTransfer": 0,
        "PIPointsWithHealthEvents": {
          "property1": {
            "MaxSeverity": 0,
            "EventId": 400001
          },
          "property2": {
            "MaxSeverity": 0,
            "EventId": 400001
          }
        },
        "AFElementsWithHealthEvents": {
          "property1": {
            "MaxSeverity": 0,
            "EventId": 400001
          },
          "property2": {
            "MaxSeverity": 0,
            "EventId": 400001
          }
        },
        "StreamCreationStatus": {
          "TransferId": "string",
          "Status": 0,
          "TotalPointStreamsExpected": 0,
          "VerifiedPointStreamsCreated": 0,
          "LastUpdateAttempt": "2019-08-24T14:15:22Z",
          "LastSuccessfulUpdate": "2019-08-24T14:15:22Z",
          "LastMessage": 0
        },
        "HistTransferProgress": {
          "TransferId": "string",
          "TotalArchives": 0,
          "CurrentArchive": 0,
          "TotalPointsInArchive": 0,
          "TransferredPointsForArchive": 0
        }
      }
    ],
    "AFIndexProgress": 0,
    "PIPointCacheProgress": 0,
    "ElementsIndexed": 0,
    "TotalElements": 0,
    "PointsIndexed": 0,
    "TotalPoints": 0
  },
  "Namespace": "string",
  "Region": "string",
  "IsDeprecated": true,
  "TransferMetrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0,
    "SuccessfulCreations": 0,
    "FailedCreations": 0,
    "SuccessfulStreamEdits": 0,
    "FailedStreamEdits": 0,
    "PointEdits": 0,
    "TotalPoints": 0,
    "AssetsCreatedPerSecond": 0,
    "AssetsProcessedCount": 0,
    "TotalAssetsInTransfer": 0,
    "FailedCreationPointIds": [
      0
    ],
    "SuccessfulStreamDeletions": 0,
    "FailedStreamDeletions": 0,
    "SuccessfulAssetDeletions": 0,
    "FailedAssetDeletions": 0,
    "SuccessfulAssetCreations": 0,
    "FailedAssetCreationsAndUpdates": 0,
    "IsModified": true,
    "SuccessfulAssetUpdates": 0
  }
}

```

---

### AgentStatus

<a id="schemaagentstatus"></a>
<a id="schema_AgentStatus"></a>
<a id="tocSagentstatus"></a>
<a id="tocsagentstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Registering|0|
|Registered|1|
|Connected|2|
|Disconnected|3|
|Deleting|4|
|RegistrationFailed|5|
|DataSourceConnectionIssue|6|
|DataSourceSecurityIssue|7|
|Shutdown|8|
|MissingConfiguration|9|

---

### PISystemDto

<a id="schemapisystemdto"></a>
<a id="schema_PISystemDto"></a>
<a id="tocSpisystemdto"></a>
<a id="tocspisystemdto"></a>

Data Transfer Object for a PI System.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ServerId|guid|false|false|None|
|Name|string|false|true|None|
|Version|string|false|true|None|
|AFServerId|guid|false|false|None|
|AFName|string|false|true|None|
|AFVersion|string|false|true|None|
|LastCommunicationTime|date-time|false|false|None|
|Transfers|[[TransferSummaryDto](#schematransfersummarydto)]|false|true|[Data Transfer Object summarizing a Transfer.]|
|AFIndexProgress|[AFIndexProgress](#schemaafindexprogress)|false|false|None|
|PIPointCacheProgress|[PIPointAttributeCacheProgress](#schemapipointattributecacheprogress)|false|false|None|
|ElementsIndexed|int64|false|false|None|
|TotalElements|int64|false|false|None|
|PointsIndexed|int64|false|false|None|
|TotalPoints|int64|false|false|None|

```json
{
  "ServerId": "string",
  "Name": "string",
  "Version": "string",
  "AFServerId": "string",
  "AFName": "string",
  "AFVersion": "string",
  "LastCommunicationTime": "2019-08-24T14:15:22Z",
  "Transfers": [
    {
      "Id": "string",
      "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
      "Description": "string",
      "Status": 0,
      "LatestStreamingRead": "2019-08-24T14:15:22Z",
      "OnPremTransferStatus": 0,
      "PIPointCount": 0,
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "SuccessfulStreamEdits": 0,
        "FailedStreamEdits": 0,
        "PointEdits": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0,
        "FailedCreationPointIds": [
          0
        ],
        "SuccessfulStreamDeletions": 0,
        "FailedStreamDeletions": 0,
        "SuccessfulAssetDeletions": 0,
        "FailedAssetDeletions": 0,
        "SuccessfulAssetCreations": 0,
        "FailedAssetCreationsAndUpdates": 0,
        "IsModified": true,
        "SuccessfulAssetUpdates": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0,
      "TransferRevisionNumber": 0,
      "LastEditDate": "2019-08-24T14:15:22Z",
      "LastEditBy": "string",
      "AutoDeleteCloudObjects": true,
      "TotalPointsInTransfer": 0,
      "PIPointsWithHealthEvents": {
        "property1": {
          "MaxSeverity": 0,
          "EventId": 400001
        },
        "property2": {
          "MaxSeverity": 0,
          "EventId": 400001
        }
      },
      "AFElementsWithHealthEvents": {
        "property1": {
          "MaxSeverity": 0,
          "EventId": 400001
        },
        "property2": {
          "MaxSeverity": 0,
          "EventId": 400001
        }
      },
      "StreamCreationStatus": {
        "TransferId": "string",
        "Status": 0,
        "TotalPointStreamsExpected": 0,
        "VerifiedPointStreamsCreated": 0,
        "LastUpdateAttempt": "2019-08-24T14:15:22Z",
        "LastSuccessfulUpdate": "2019-08-24T14:15:22Z",
        "LastMessage": 0
      },
      "HistTransferProgress": {
        "TransferId": "string",
        "TotalArchives": 0,
        "CurrentArchive": 0,
        "TotalPointsInArchive": 0,
        "TransferredPointsForArchive": 0
      }
    }
  ],
  "AFIndexProgress": 0,
  "PIPointCacheProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0,
  "PointsIndexed": 0,
  "TotalPoints": 0
}

```

---

### TransferSummaryDto

<a id="schematransfersummarydto"></a>
<a id="schema_TransferSummaryDto"></a>
<a id="tocStransfersummarydto"></a>
<a id="tocstransfersummarydto"></a>

Data Transfer Object summarizing a Transfer.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|HistoricalDataStartTime|date-time|false|false|None|
|Description|string|false|true|None|
|Status|[TransferStatus](#schematransferstatus)|false|false|None|
|LatestStreamingRead|date-time|false|false|None|
|OnPremTransferStatus|[TransferJobStatus](#schematransferjobstatus)|false|false|None|
|PIPointCount|int32|false|false|None|
|Metrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|Data Transfer Object for tracking metrics of a Transfer.|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out. Low filters all but 3 metadata items. Medium only filters out 2 metadata items. High means no data is filtered out.|
|TransferRevisionNumber|int32|false|false|None|
|LastEditDate|date-time|false|false|None|
|LastEditBy|guid|false|false|None|
|AutoDeleteCloudObjects|boolean|false|false|None|
|TotalPointsInTransfer|int64|false|false|None|
|PIPointsWithHealthEvents|object|false|true|None|
|AFElementsWithHealthEvents|object|false|true|None|
|StreamCreationStatus|[DetailedStreamCreationStatus](#schemadetailedstreamcreationstatus)|false|true|None|
|HistTransferProgress|[HistoricalTransferProgress](#schemahistoricaltransferprogress)|false|true|None|

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "OnPremTransferStatus": 0,
  "PIPointCount": 0,
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0,
    "SuccessfulCreations": 0,
    "FailedCreations": 0,
    "SuccessfulStreamEdits": 0,
    "FailedStreamEdits": 0,
    "PointEdits": 0,
    "TotalPoints": 0,
    "AssetsCreatedPerSecond": 0,
    "AssetsProcessedCount": 0,
    "TotalAssetsInTransfer": 0,
    "FailedCreationPointIds": [
      0
    ],
    "SuccessfulStreamDeletions": 0,
    "FailedStreamDeletions": 0,
    "SuccessfulAssetDeletions": 0,
    "FailedAssetDeletions": 0,
    "SuccessfulAssetCreations": 0,
    "FailedAssetCreationsAndUpdates": 0,
    "IsModified": true,
    "SuccessfulAssetUpdates": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string",
  "AutoDeleteCloudObjects": true,
  "TotalPointsInTransfer": 0,
  "PIPointsWithHealthEvents": {
    "property1": {
      "MaxSeverity": 0,
      "EventId": 400001
    },
    "property2": {
      "MaxSeverity": 0,
      "EventId": 400001
    }
  },
  "AFElementsWithHealthEvents": {
    "property1": {
      "MaxSeverity": 0,
      "EventId": 400001
    },
    "property2": {
      "MaxSeverity": 0,
      "EventId": 400001
    }
  },
  "StreamCreationStatus": {
    "TransferId": "string",
    "Status": 0,
    "TotalPointStreamsExpected": 0,
    "VerifiedPointStreamsCreated": 0,
    "LastUpdateAttempt": "2019-08-24T14:15:22Z",
    "LastSuccessfulUpdate": "2019-08-24T14:15:22Z",
    "LastMessage": 0
  },
  "HistTransferProgress": {
    "TransferId": "string",
    "TotalArchives": 0,
    "CurrentArchive": 0,
    "TotalPointsInArchive": 0,
    "TransferredPointsForArchive": 0
  }
}

```

---

### TransferStatus

<a id="schematransferstatus"></a>
<a id="schema_TransferStatus"></a>
<a id="tocStransferstatus"></a>
<a id="tocstransferstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|NotSet|0|
|Started|1|
|Stopped|2|
|Initializing|3|

---

### TransferJobStatus

<a id="schematransferjobstatus"></a>
<a id="schema_TransferJobStatus"></a>
<a id="tocStransferjobstatus"></a>
<a id="tocstransferjobstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Idle|0|
|SendingHistoricalData|1|
|SendingStreamingData|2|
|BackfillingStreamingGap|4|
|Done|8|
|UncategorizedError|16|
|StreamingErrorConsumerRemoved|32|
|StreamingErrorUpdateQueueOverflow|64|
|StreamingErrorSignupDropped|128|
|StreamingErrorProducerRemoved|256|
|StreamingErrorUnknown|512|
|PIPointTypeChangeDetected|1024|
|CreatingStreams|2048|
|NoValidPIPointsInTransfer|4096|
|UpdatingTransfer|8192|
|LastEditFailed|16384|

---

### TransferMetricsDto

<a id="schematransfermetricsdto"></a>
<a id="schema_TransferMetricsDto"></a>
<a id="tocStransfermetricsdto"></a>
<a id="tocstransfermetricsdto"></a>

Data Transfer Object for tracking metrics of a Transfer.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamingEventCountPerSecond|float|false|false|None|
|HistoricalEventCountPerSecond|float|false|false|None|
|SuccessfulCreations|int64|false|false|None|
|FailedCreations|int64|false|false|None|
|SuccessfulStreamEdits|int64|false|false|None|
|FailedStreamEdits|int64|false|false|None|
|PointEdits|int64|false|false|None|
|TotalPoints|int64|false|false|None|
|AssetsCreatedPerSecond|float|false|false|None|
|AssetsProcessedCount|int64|false|false|None|
|TotalAssetsInTransfer|int64|false|false|None|
|FailedCreationPointIds|[integer]|false|true|None|
|SuccessfulStreamDeletions|int64|false|false|None|
|FailedStreamDeletions|int64|false|false|None|
|SuccessfulAssetDeletions|int64|false|false|None|
|FailedAssetDeletions|int64|false|false|None|
|SuccessfulAssetCreations|int64|false|false|None|
|FailedAssetCreationsAndUpdates|int64|false|false|None|
|IsModified|boolean|false|false|None|
|SuccessfulAssetUpdates|int64|false|false|None|

```json
{
  "StreamingEventCountPerSecond": 0,
  "HistoricalEventCountPerSecond": 0,
  "SuccessfulCreations": 0,
  "FailedCreations": 0,
  "SuccessfulStreamEdits": 0,
  "FailedStreamEdits": 0,
  "PointEdits": 0,
  "TotalPoints": 0,
  "AssetsCreatedPerSecond": 0,
  "AssetsProcessedCount": 0,
  "TotalAssetsInTransfer": 0,
  "FailedCreationPointIds": [
    0
  ],
  "SuccessfulStreamDeletions": 0,
  "FailedStreamDeletions": 0,
  "SuccessfulAssetDeletions": 0,
  "FailedAssetDeletions": 0,
  "SuccessfulAssetCreations": 0,
  "FailedAssetCreationsAndUpdates": 0,
  "IsModified": true,
  "SuccessfulAssetUpdates": 0
}

```

---

### DataPrivacy

<a id="schemadataprivacy"></a>
<a id="schema_DataPrivacy"></a>
<a id="tocSdataprivacy"></a>
<a id="tocsdataprivacy"></a>

None means all metadata is filtered out. Low filters all but 3 metadata items. Medium only filters out 2 metadata items. High means no data is filtered out.

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Undefined|0|
|Medium|1|
|None|2|
|High|3|
|Low|4|

---

### HealthEventSummaryDto

<a id="schemahealtheventsummarydto"></a>
<a id="schema_HealthEventSummaryDto"></a>
<a id="tocShealtheventsummarydto"></a>
<a id="tocshealtheventsummarydto"></a>

This class holds the highest severity among all health events for some object (currently either a point or element) and *some* eventId of a health event with this severity. There may be multiple health events of the highest severity, but we just need 1 event id to return to the UI for display.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|MaxSeverity|[LogLevel](#schemaloglevel)|false|false|The highest severity among all health events related to the object being summarized|
|EventId|[EventIds](#schemaeventids)|false|false|The eventId of some health event with a severity equal to MaxSeverity associated with the object being summarized|

```json
{
  "MaxSeverity": 0,
  "EventId": 400001
}

```

---

### LogLevel

<a id="schemaloglevel"></a>
<a id="schema_LogLevel"></a>
<a id="tocSloglevel"></a>
<a id="tocsloglevel"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Trace|0|
|Debug|1|
|Information|2|
|Warning|3|
|Error|4|
|Critical|5|
|None|6|

---

### EventIds

<a id="schemaeventids"></a>
<a id="schema_EventIds"></a>
<a id="tocSeventids"></a>
<a id="tocseventids"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|StoppingAgent|400001|
|StoppedAgent|400002|
|ErrorDisposingServiceLocator|400003|
|ProblemSyncingWithTheConfigService|400004|
|SocketErrorDuringSendAgentStatus|400005|
|UnexpectedExceptionTerminatingSyncProcess|400006|
|ExitingConfigSyncManagerRunAsync|400007|
|StoppingConfigSyncManager|400008|
|AttemptingToStopConfigSyncManager|400009|
|StoppedConfigSyncManager|400010|
|ConfigSyncResponseContentUnrecognizedFormat|400011|
|UnexpectedTransportMessageFromConfigSync|400012|
|FailureInLogForwarding|400013|
|TimedOutStoppingCheckCacheAndSendLogsAsync|400014|
|FailedToSendLogMessagesToOcsWillRetry|400015|
|TimedOutConnectingToDataArchive|400016|
|ErrorConnectingToDataArchiveWillRetry|400017|
|ConnectedToDataArchive|400018|
|ErrorPerformingQuery|400019|
|FailedToGetDataArchiveInfoRetrying|400020|
|FailedToGetDataArchiveInfo|400021|
|FailedToPerformQueryForTransferRetrying|400022|
|FailedToPerformQueryForTransfer|400023|
|DataArchiveVersionNotSupported|400024|
|FailedToPerformQueryRetrying|400025|
|FailedToPerformQuery|400026|
|FailedToPerformQueryElementInvalid|400027|
|ConfiguredConnectionsToOcs|400028|
|CreatingOrVerifyingAgentRegistration|400029|
|AgentRegistrationCompleted|400030|
|AgentRegistrationInProgress|400031|
|AgentRegistrationFailedWillRetry|400032|
|AgentRegistrationFailed|400033|
|BadResponseFromConfigSyncEndpoint|400034|
|ErrorTryingToSyncWithConfigService|400035|
|BadResponseSendingForwardedLogs|400036|
|ErrorTryingToSendForwardedLogs|400037|
|BadResponseSendingQueryResults|400038|
|SentQueryResults|400039|
|ErrorSendingQueryResults|400040|
|HttpClientFailedToWriteDataToDataService|400041|
|WroteTransportMessagesToDataService|400042|
|ErrorSendingDataToDataService|400043|
|WaitingForAgentServicesToBeReady|400044|
|TimedOutWaitingForAgentServicesToBeReady|400045|
|InvalidMessageTypeReceivedForStreamCreation|400046|
|StreamCreationRequestFailed|400047|
|ErrorSendingRequestToCreateStreams|400048|
|StatusRequestFailedWaitingForStreamCreation|400049|
|StreamCreationInOcsFailed|400050|
|FailedToVerifyStreamCreationForPoints|400051|
|CleaningUpAfterStreamCreationFailed|400052|
|StreamCreationOrVerificationSucceeded|400053|
|ErrorCleaningUpAfterStreamCreation|400054|
|AgentServiceRetrievedSecrets|400055|
|AgentWillTerminateDueToUnhandledException|400056|
|ErrorShuttingDownAgentService|400057|
|AgentShuttingDownDueToUnhandledException|400058|
|AgentServiceHostStarted|400059|
|AgentReceivedUnregisterRequest|400060|
|AgentUnregisterWasRequestedWithInvalidSpec|400061|
|AgentUnregistered|400062|
|QueryRequestFromConfigService|400063|
|SendingQueryResultsToConfigService|400064|
|ProcessingTransferJobRequest|400065|
|ProcessingTransferStopRequest|400066|
|StoppingAllTransferJobs|400067|
|ShutdownRequestReceivedWhileWritingDataToOcs|400068|
|ErrorWritingToOcs|400069|
|DoneTransferringDataToOcsForTransferStep|400070|
|ErrorWhileWritingDataToOcs|400071|
|HistoricalEventsChunkSentOutOfOrder|400072|
|SpecifiedStartTimeInTheFutureForHistoricalData|400073|
|GettingPagedDataRetryingForPoint|400074|
|GettingPagedDataFailedForPoint|400075|
|FailedToGetDataForPointAndRetrying|400076|
|GettingPagedDataForPointAsDataExceededMaxArcCollect|400077|
|FailedToGetDataForPoint|400078|
|TransferringEventsForPoint|400079|
|BusySendingDataToOcsCannotQueueMore|400080|
|StartingHistoricalDataTransfer|400081|
|WaitingToGetStartTimeOfStreamingUpdates|400082|
|SettingEndOfHistoricalRecoveryPeriod|400083|
|HistoricalStepWaitingForBackFillingStreamingData|400084|
|BackfillingStreamingDataOverBeginningHistoricalTransferStep|400085|
|AgentShutdownRequestedWhileRetrievingDataArchiveInfo|400086|
|UnableToGetArchiveInfoFromDataArchive|400087|
|BusyReadingFromDataArchiveCannotRequestMoreData|400088|
|ShutdownRequestReceivedWhileReadingHistoricalDataFromDataArchive|400089|
|ErrorReadingFromDataArchive|400090|
|DoneReadingDataFromDataArchiveForTransferStep|400091|
|TimedOutWaitingToSignUpForStreamingUpdates|400092|
|StartingStreamingDataTransfer|400093|
|RecievedDataLossNotificationOnDataArchive|400094|
|RegisteredForStreamingUpdatesOnDataArchiveAsConsumer|400095|
|FailedToGetStreamingUpdatesFromDataArchive|400096|
|FailedToGetStreamingUpdatesFromDataArchiveRetrying|400097|
|StreamingUpdatesForPointsWillSendData|400098|
|SendingStreamingUpdates|400099|
|StoppingStreamingDataTransfer|400100|
|StopAlreadyStoppedStreamingDataTransferStepRequested|400101|
|StartingTransferJob|400102|
|StoppingTransferJob|400103|
|NoProgressAvailableForTransferNotStartedSendingDataYet|400104|
|HistoricalDataToOcsCompletedButNoStatusForTheStepAvailable|400105|
|HistoricalDataToOcsCompletedButTheStepStatusIsNotCompleted|400106|
|TransferInProgressCannotStartAgain|400107|
|GotTransferJobIdFromConfigService|400108|
|TransferManagerPreparingForTransferOfPoints|400109|
|UnrecoverableErrorAcquiringPointMetaData|400110|
|UnableToFindSupportedPITagsOnDataArchive|400111|
|CreatingOrVerifyingStreamsInOcsForPIPoints|400112|
|TransferManagerCreatingPIDataTransferJob|400113|
|ErrorTransferringDataToDataService|400114|
|TransferManagerGotStopTransferRequest|400115|
|UnableToStopTransferJobCouldNotFindTransfer|400116|
|TransferManagerStoppingTransferJobs|400117|
|DeleteClientCredentialsAndExit|400118|
|UnknownCustomServiceCommand|400119|
|UnexpectedNonFatalErrorInSendAgentStatus|400120|
|FatalErrorWritingToOcs|400121|
|UnexpectedErrorWritingToOcs|400122|
|ErrorWhileStoppingTransferTasks|400123|
|FatalErrorStartingAgent|400124|
|UsingSettingsFileMessage|400125|
|SignUpForArchiveUpdatesErrorForSingleStream|400126|
|SigningUpForArchiveUpdates|400127|
|RetrievedPointsFromDataArchiveForArchiveUpdates|400128|
|AbortingWaitForStreamsCreationDueToPIPointTypeChangeDetected|400129|
|UnableToRetrieveConfigurationalFileInformation|400130|
|UnableToReadConfigurationalFileInformation|400131|
|DataArchiveVersionChangeDetected|400132|
|UnsupportedPointTypeInTransferRequest|400133|
|MissingQueryResults|400134|
|MultipleQueryClients|400135|
|MissingQueryClient|400136|
|MissingInformationForPIPointResult|400137|
|ErrorSendingRequestToUpdateStreams|400138|
|InvalidIdentityServiceClient|400139|
|ErrorTryingToPublishCapabilities|400140|
|PublishedCapabilities|400141|
|ErrorTryingToSerializeCapabilities|400142|
|ErrorTryingToPostCapabilities|400143|
|BadResponseCodePublishingCapabilities|400144|
|FailedToRetrieveStreamNameFromTransfer|400145|
|TagNotFound|400146|
|MetadataChangeFound|400147|
|TagUpdate|400148|
|GetOrUpdateStreamMetadata|400149|
|FailedToRetrieveStreamMetadata|400150|
|GetTransferFromTransferManager|400151|
|NextUpdateOccursInXTime|400152|
|FailedToGetStreamData|400153|
|TaskCancelledExceptionOccurred|400154|
|ErrorTryingToSyncCapabilities|400155|
|GetCapabilityUpdates|400156|
|ErrorTryingToGetCapabilities|400157|
|CapabilityUpdatesEmptyMissing|400158|
|ConnectedToAFServer|400159|
|StartingAFDataTransfer|400160|
|ShutdownRequestReceivedWhileReadingFromAFServer|400161|
|ErrorReadingFromAFServer|400162|
|DoneReadingDataFromAFServerForTransferStep|400163|
|AFVersionNotSupported|400164|
|ErrorConnectingToAssetFrameworkWillRetry|400165|
|TransferringAFMessage|400166|
|BusyReadingFromAFServerCannotRequestMoreData|400167|
|StartedConfigTool|400168|
|SavedAgentConfiguration|400169|
|UnexpectedErrorInConfigTool|400170|
|ConfigToolFailedToStartService|400171|
|ConfigToolFailedToStopService|400172|
|ChangedAgentConfiguration|400173|
|ConfigToolFailedToGetAFServerIPAddress|400174|
|ConfigToolFailedToGetDAServerIPAddress|400175|
|HostnameUpdated|400176|
|PublishPointsFromAF|400177|
|BadResponseCodePublishingPointsFromAF|400178|
|ErrorTryingToSerializePointsFromAF|400179|
|ErrorTryingToPutPointsFromAF|400180|
|AddingPointsReferencedByAFToTransfer|400181|
|ErrorRemovingAFObjectFromCache|400182|
|FeatureFailure|400183|
|AssetFrameworkVersionChangeDetected|400184|
|WaitingForDataServicesToBeReady|400185|
|WaitingForAssetsServiceToBeReady|400186|
|WaitingForStreamsServiceToBeReady|400187|
|ConfigToolUserNotADomainUser|400188|
|AssetFrameworkIndexingCompleted|400189|
|AssetFrameworkIndexingProgress|400190|
|AssetFrameworkIndexingFailed|400191|
|BadResponseSendingAFIndexProgress|400192|
|SentAFIndexProgress|400193|
|ErrorSendingAFIndexProgress|400194|
|PossibleDataCorruptionDetected|400195|
|GotIngressMessage|400196|
|StreamNotInUpdateContext|400197|
|AssetFrameworkMismatchedUOM|400198|
|AssetFrameworkMismatchedUOMSummary|400199|
|ErrorResolvingPIPointAttributeForAsset|400200|
|StartedAgent|400201|
|UnexpectedFatalErrorInSendAgentStatus|400202|
|UnexpectedErrorSerializingMessage|400203|
|PIPointWithTypeChangeIgnoredInTransfer|400204|
|NoValidPIPointsInTransfer|400205|
|FailedToDeserializeStreamCreationStatus|400206|
|ConfigToolFailedToLogIntoOCS|400207|
|ConfigToolFailedToGetTenantId|400208|
|ConfigToolFailedToGetUserId|400209|
|ConfigToolFailedToGetRoles|400210|
|ConfigToolUserLoggedIntoDifferentTenant|400211|
|ConfigToolUserHasInsufficientOCSPermissions|400212|
|ConfigToolIEEnhancedSecurityEnabled|400213|
|ConfigToolWindowsRegisteryError|400214|
|ConfigToolDAAlreadyRegistered|400215|
|UnknownObjectInTransferCache|400216|
|StreamingDataTransferStepCancelled|400217|
|FailedToRemoveTransferCacheFiles|400218|
|StartingAgent|400219|
|EmptyAgentIdDetected|400220|
|StreamingTransferErrorStatus|400221|
|PISystemNotOwnedByAgent|400222|
|ErrorPerformingSimplePIPointDataReferenceCheck|400223|
|LoggerCreated|400224|
|ElementFound|400225|
|PossibleMalformedSubstitution|400226|
|UnexpectedHttpRequestException|400227|
|GetPISystemsFromConfigService|400228|
|GetAgentFromConfigService|400229|
|GetDataSourcesFromConfigService|400230|
|DeletePISystemsFromConfigService|400231|
|UnsupportedRegistrationMessageTypeForAgentVersion|400232|
|ConfigToolFailedToRetrieveOCSRegisteredDataArchives|400233|
|ConfigToolFailedToRetrieveAgentInformation|400234|
|ErrorConnectingToAssetFramework|400235|
|ConfigToolUserNotAServerAdmin|400236|
|WarningStreamingFutureData|400237|
|UnableToSetDefaultPIDataArchive|400238|
|ConfigToolDetectingNoDataArchives|400239|
|ConfigToolResolvedDefaultPIServerError|400240|
|ErrorConnectingToDataArchive|400241|
|WarningSendingRequestWithNoPartitionKey|400242|
|WarningSendingRequestWithDefaultPartitionKey|400243|
|ErrorSettingDesiredStatusInitializing|400244|
|PointTransferLogEmpty|400245|
|TransferJobReceivedEditTransferRequest|400246|
|TransferJobReceivedEditTransferRequestWhileCreatingStreams|400247|
|TraceProcessingTransferJobRequest|400248|
|TraceGotTransferJobIdFromConfigService|400249|
|TraceCreatingHistoricTransferStep|400250|
|TraceCalculatedTimeContexts|400251|
|TracePointDataRequestParameters|400252|
|CacheFileWritten|400253|
|DeleteStreamFromContextPointsNotFound|400254|
|PIPointAttributeCacheStarted|400255|
|PIPointAttributeCacheFinished|400256|
|PIPointAttributeCacheLoadedPIPoints|400257|
|FailedDeletingHealthEvents|400258|
|StreamCreationForEditTransfer|400259|
|StreamCreationForEditTransferError|400260|
|EditTransferFailed|400261|
|NewDataUpdateContextAdded|400262|
|RetrieveTransferMetricsRequestFailed|400263|
|FailedPointIdIgnoredFromStreamMetadata|400264|
|BadResponseSendingPIPointCacheProgress|400265|
|SentPIPointCacheProgress|400266|
|ErrorSendingPIPointCacheProgress|400267|
|InvalidMessageTypeReceivedForStreamDeletion|400268|
|StreamDeletionRequestFailed|400269|
|ErrorSendingRequestToDeleteStreams|400270|
|FailedSendingHealthEventFromAgent|400271|
|PIConnectionErrorGettingHistoricalEvents|400272|
|PIAuthenticationErrorGettingHistoricalEvents|400273|
|HistoricalStepStatusChanged|400274|
|HistoricalStepEditRequestReceived|400275|
|WaitForOnPremTransferStatusToUpdate|400276|
|TransferManagerSendingEditNotification|400277|
|TracePointTransferLogAddingUpdatingLastEvent|400278|
|TracePointTransferLogBulkUpdateLastEventTimestamps|400279|
|MappingCreationFailed|400280|
|DataArchiveServerIdNotSupported|400281|
|TracePointTransferLogLoaded|400282|
|ErrorReadingPointTransferLog|400283|
|UncategorizedErrorOnPremDuringTransfer|400284|
|UnexpectedErrorDuringStreamCreation|400285|
|PIPointAttributeCacheCannotRefresh|400286|
|CacheFileRead|400287|
|NoReadAccessSecureObjectDataArchive|400288|
|BadResponseCodeCreatingAgentHealthEvent|400289|
|ErrorTryingToSerializeAgentHealthEvent|400290|
|ErrorTryingToCreateAgentHealthEvent|400291|
|CreatingAgentHealthEvent|400292|
|ErrorDeletingPointTransferLog|400293|
|PointTransferLogFileRenamed|400294|
|AssetFrameworkRecreatingCacheFile|400295|
|ErrorReadingCacheFile|400296|
|ErrorWritingCacheFile|400297|
|ErrorDisposingLock|400298|
|TimedOutVerifyingDataArchiveDisplayName|400299|
|DataArchiveNameChangeDetected|400300|
|DeletedAgentHealthEvents|400301|
|AFIndexModified|400302|
|PIPointTypeMismatch|400303|
|PointAttributeUomConflict|400304|
|PointReferenceUomNotInCache|400305|
|ShutdownRequestReceivedWhileSyncingSdsUnitsOfMeasure|400306|
|StartingPointAttributeUomTransferStep|400307|
|ErrorWhilePointAttributeUomTransferStep|400308|
|ReadingSupportedUnitsOfMeasureFromOcs|400309|
|FailedToLoadUnitsOfMeasureFromOcs|400310|
|ErrorDeletingCacheFile|400311|
|UnknownPIPointCompressionType|400312|
|ErrorRetrievingLastArchiveValue|400313|
|RegisteringServiceType|410000|
|RegisteredServiceType|410001|
|FailedToRegisterServiceType|410002|
|LeavingServiceTypeHostProcess|410003|
|AppInsightKeysNotFound|410004|
|GenericProvisioningNotificationException|420000|
|ReceivedRemoveTenantRequest|420001|
|RemovedTenant|420002|
|FailedToRemoveTenant|420003|
|ReceivedDeactivateTenantRequest|420004|
|DeactivatedTenant|420005|
|FailedToDeactivateTenant|420006|
|ReceivedReactivateTenantRequest|420007|
|ReactivatedTenant|420008|
|FailedToReactivateTenant|420009|
|ReceivedCreateNamespaceRequest|420010|
|CreatedNamespace|420011|
|FailedToCreateNamespace|420012|
|ReceivedDeleteNamespaceRequest|420013|
|DeletedNamespace|420014|
|FailedToDeleteNamespace|420015|
|ProvisionerServiceConstructed|420016|
|ProvisionerServiceBeganRunAsync|420017|
|StartingProvisioningHandler|420018|
|StartedProvisioningHandler|420019|
|FailedToRegisterForProvisioningFromNexus|420020|
|FailedToRetrieveListOfTenants|420021|
|IgnoringTenantForProvisioning|420022|
|FailedToRetrieveNamespacesForTenant|420023|
|StartingProvisioningForNamespace|420024|
|FailedToProvisionForNamespace|420025|
|SFRuntimeRequestedServiceShutdown|420026|
|ProvisionerServiceShuttingDownDueToUnhandledException|420027|
|StoppingProvisioningHandler|420028|
|FailedToStopProvisioningHandler|420029|
|ProvisionerServiceLeavingRunAsync|420030|
|ExceptionWhenProvisioningTenant|420031|
|ExceptionWhenDeprovisioningTenant|420032|
|IgnoringRequestToProvisionNamespaceResourcesForTenant|420033|
|ProvisioningProcessorProvisionedResourcesForTenant|420034|
|NamespaceProvisioningFailed|420035|
|ProvisioningProcessorDeprovisionedNamespace|420036|
|NamespaceDeprovisioningFailed|420037|
|BeganRunningCreateConfigServiceAsync|420038|
|CreatedConfigService|420039|
|ConfigServiceAlreadyExistsForNamespace|420040|
|LeavingCreateConfigServiceAsync|420041|
|BeganRunningCreateManagementServiceAsync|420042|
|CreatedManagementService|420043|
|ManagementServiceAlreadyExistsForNamespace|420044|
|LeavingCreateManagementServiceAsync|420045|
|BeganRunningDeleteServiceAsync|420046|
|DeletedService|420047|
|UnableToDeleteService|420048|
|LeavingDeleteServiceAsync|420049|
|PreviousOperationTaskWasFaulted|420050|
|FailedToAddOperationForTypeAlreadyActive|420051|
|OperationNotFoundAmongActiveOperations|420052|
|OperationCannotBeRemovedSinceNotComplete|420053|
|OperationFaultedOrCanceled|420054|
|OperationCannotBeRemovedSinceNotFaulted|420055|
|OperationWillBeRemovedSinceFaulted|420056|
|OperationFaulted|420057|
|StartingProvisioningSynchronizer|420058|
|FailedToUpdateNamespaceScopedResourcesForAgents|420059|
|FailedToDeleteNamespaceScopedResourcesForAgents|420060|
|NotAllNamespaceScopedResourcesFound|420061|
|FailedCheckingNamespaceScopedResources|420062|
|InvalidRegionReceivedFromProvisioningNotification|420063|
|ReceivedUpdateNamespaceRequest|420064|
|UpdatedNamespace|420065|
|FailedToUpdateNamespace|420066|
|ProvisionerServiceClosing|420067|
|ProvisionerServiceAborting|420068|
|ProvisionerServiceStartingKestrel|420069|
|InvalidNamespaceStatusForProvisioningNotification|420070|
|StartingElasticPoolWorker|420071|
|StoppingElasticPoolWorker|420072|
|BeganRunningCreateOrUpdateDatabaseWithRetryAsync|420073|
|DataSourceOwnerIsMissing|430000|
|DataSourceOwnerIsMalformed|430001|
|RequestContentLengthMismatch|430002|
|ErrorForwardingLogsFromAgent|430003|
|ProcessedTransportMessage|430004|
|ProcessedRequestToPostAsyncForAgent|430005|
|ErrorSyncingStatusOfAgent|430006|
|ProcessingAgentSyncRequestWithTransferJobStatus|430007|
|InformingAgentOfDeletedTransfer|430008|
|GeneratingAgentUnregisterTransportMessage|430009|
|AttemptedRegisterWithIncorrectConfig|430010|
|AttemptedRegisterDeletedAgent|430011|
|KnownAgentRegisterInvalidDataSource|430012|
|NewAgentRegisterNonExistentDataSource|430013|
|ReconnectedRegisteredAgent|430014|
|PISystemRegisteredToAnotherAgent|430015|
|PISystemPreviouslySoftDeleted|430016|
|PISystemNameTooSimilarToRegistered|430017|
|FailedToStartProvisioningResourcesForAgent|430018|
|FailedToCompleteProvisioningForAgent|430019|
|RemovedFaultedProvisioningTaskForAgent|430020|
|FailedToRemoveFaultedProvisioningTaskForAgent|430021|
|RegisteredTheAgent|430022|
|FailedToRemoveAgentProvisioningTaskFromCollection|430023|
|ProcessingPointQueryResultWithQueryId|430024|
|FailedToRemovePointQueryForAgent|430025|
|DeletingTransferWithStatus|430026|
|FailedToStartDeletingResourcesForAgent|430027|
|FailedToCompleteDeletionOfResourcesForAgent|430028|
|FailedToRemoveAgentResourcesDeletingTaskFromCollection|430029|
|MissingCollectionAclForDataSources|430030|
|ConfigServiceConstructed|430031|
|ConfigServiceShuttingDownDueToUnhandledException|430032|
|ConfigServiceStartingKestrel|430033|
|ConfigServiceClosing|430034|
|StartingDeprovisioningAllAgentResources|430035|
|FinishedDeprovisioningAllAgentResources|430036|
|AgentResourcesNotDeprovisioned|430037|
|FinishedDeprovisioningAgentResources|430038|
|MaintenanceTasksFaulted|430039|
|AgentResourcesNotProvisioned|430040|
|FinishedProvisioningAgentResources|430041|
|FailedToVerifyAgentResourcesConsistent|430042|
|UpdatedAgentVersionForExistingAgent|430043|
|FailedToDownloadAgentSetupKit|430044|
|DataSourceUsedByOtherAgent|430045|
|FailedToGetAgentSetupKitInfo|430046|
|DeletedAgentForwardedLogs|430047|
|FailedToRetrieveTransferMetrics|430048|
|CreatedDataSource|430049|
|UpdatedDataSource|430050|
|DeletedDataSource|430051|
|OnPremTransferJobStatusChangeDetected|430052|
|ProcessingQueryResultWithQueryId|430053|
|FailedToRemoveQueryForAgent|430054|
|ErrorProcessingAgentCapabilityPublishing|430055|
|ConfigServiceAborting|430056|
|ErrorSendingAgentCapabilityUpdates|430057|
|InitiatingCapabilitySyncRequest|430058|
|ConfigServiceCapabilitySyncRequest|430059|
|CapabilitySyncManagerSyncError|430060|
|CapabilitySyncManagerGetUpdatesError|430061|
|UpdatedPISystem|430062|
|UpdatedAgent|430063|
|AddedQueryToAgentResponseMessages|430064|
|FailedToAddQueryToAgentResponseMessages|430065|
|AddedPointQueryToAgentResponseMessages|430066|
|FailedToAddPointQueryToAgentResponseMessages|430067|
|PagingRequestOnAgentWithoutSupport|430068|
|AgentUsedByOtherDataSource|430069|
|AttemptedRegisterDeprecatedAgent|430070|
|FailedToRetrieveTunableParameters|430071|
|FailedToUpdateTransferMetrics|430072|
|AgentRegisteredWithCapabilities|430073|
|FailedToPublishCapabilitiesDuringRegistration|430074|
|NoCapabilitiesReturnedFromRegistration|430075|
|ErrorUpdatingAgentTransferAssetCreationCounts|430076|
|ErrorDeletingClient|430077|
|FailedToReadDataFromOCS|430078|
|ReadingFromOcs|430079|
|AssetFrameworkUOMNotInCache|430080|
|AgentAFReIndexRequested|430081|
|ErrorGettingFeatureFlagStatus|430082|
|AgentTransferUpdateErrorBadType|430083|
|AgentTransferUpdateErrorNullStatus|430084|
|AgentTransferUpdateErrorEmptyGuid|430085|
|AgentTransferUpdateErrorAgentRevTooHigh|430086|
|AgentTransferUpdateTransferUpdateRequested|430087|
|FailedToRemoveAgentHealthEvents|430088|
|RequestedAgentNotFound|430089|
|ErrorParsingDataSourceOwner|430090|
|AgentPIReIndexRequested|430091|
|FailedToGetAgentStatus|430092|
|FailedToCancelQueryForAgent|430093|
|DeletingTransferCloudObject|430094|
|ErrorWritingDataToEventHub|440000|
|CreatingStreamsForTransferJob|440001|
|ErrorCreatingStreamsFromMetadataForTransferJob|440002|
|FailedToGetStatusForStreamCreationForTransferJob|440003|
|DeletedCompletedStreamCreationTaskForTransferJob|440004|
|EventProcessorShuttingDown|440005|
|SimpleEventProcessorInitialized|440006|
|EventProcessErrorOnPartition|440007|
|ProcessSingleEventAsyncFailedDueToUnhandledException|440008|
|DeserializedDataServiceInitializationData|440009|
|BuiltEventHubClient|440010|
|DataServiceConstructed|440011|
|ExceptionWhileCreatingDataService|440012|
|DataServiceBeganRunAsync|440013|
|RegisteredForEventProcessorHost|440014|
|DataServiceShuttingDownDueToUnhandledException|440015|
|DataServiceLeavingRunAsync|440016|
|DataServiceClosing|440017|
|UnableToUnregisterEventProcessorForEventHub|440018|
|UnregisteredEventProcessorForEventHub|440019|
|ExceptionAttemptingUnregisterEventProcessor|440020|
|ErrorCreatingOrUpdatingMetadataForStream|440021|
|ErrorCreatingOrUpdatingStream|440022|
|ErrorWritingEventsForStream|440023|
|ErrorGettingDataSourceOwner|440024|
|HttpSdsRequestSinkSendError|440025|
|ErrorDeserializingMetadataResponseForStream|440026|
|ErrorDeserializingStreamResponseFromSds|440027|
|UsingRootManageAccessKeyForEventHub|440028|
|UsingLowPrivilegeAccessKeysForEventHub|440029|
|StreamExistsWithADifferentTypeInSDS|440030|
|DataServiceAborting|440031|
|DataServiceStartingKestrel|440032|
|HttpAssetRequestSinkError|440033|
|DeserializedAssetsServiceInitializationData|440034|
|AssetsServiceConstructed|440035|
|ExceptionWhileCreatingAssetsService|440036|
|AssetsServiceStartingKestrel|440037|
|AssetsServiceBeganRunAsync|440038|
|AssetsServiceShuttingDownDueToUnhandledException|440039|
|AssetsServiceLeavingRunAsync|440040|
|AssetsServiceClosing|440041|
|AssetsServiceAborting|440042|
|DeserializedStreamsServiceInitializationData|440043|
|StreamsServiceConstructed|440044|
|ExceptionWhileCreatingStreamsService|440045|
|StreamsServiceStartingKestrel|440046|
|StreamsServiceBeganRunAsync|440047|
|StreamsServiceShuttingDownDueToUnhandledException|440048|
|StreamsServiceLeavingRunAsync|440049|
|StreamsServiceClosing|440050|
|StreamsServiceAborting|440051|
|AssetsServiceMultiStatusResponse|440052|
|FailedToCreateOrUpdateAsset|440053|
|FailedToCreateOrUpdateAssetType|440054|
|ErrorCreatingAssetsGeneric|440055|
|ErrorCreatingAssetsDetailed|440056|
|ExceptionWhileRetrievingAssetsEventHub|440057|
|IgnoringEvent|440058|
|UnexpectedErrorInEventHubProcessor|440059|
|EventHubInitializationData|440060|
|IgnoringMessage|440061|
|MessageSentToStreamsService|440062|
|MessageSentToAssetsService|440063|
|DataServiceFailedToCreateStream|440064|
|DataServiceFailedToUpdateStreamMetadata|440065|
|StreamsServiceFailedToUpdateValuesInSDS|440066|
|ErrorRetrievingStreamPartitionMapping|440067|
|WarningNoPartitionIdReceived|440068|
|WarningEmptyPartitionIdReceived|440069|
|DataServiceFailedToUpdateStream|440070|
|DataServiceFailedToUpdateFailedStreamsPointIdList|440071|
|DataServiceFailedToFindStreamDuringDelete|440072|
|DataServiceFailedToDeleteStream|440073|
|DeletingStreamsForTransferJob|440074|
|ErrorDeletingStreamsForTransferJob|440075|
|DataSourceOwnerIdentityCacheTrusteeTypeNotImplemented|440076|
|FailedToAddNewHealthEventFromAssetService|440077|
|FailedToAddNewHealthEvent|440078|
|AssetServiceFailedToDeleteAsset|440079|
|AssetServiceFailedToDeleteAssetType|440080|
|ConfigurationServiceBeganRunAsync|440081|
|ConfigurationServiceShuttingDownDueToUnhandledException|440082|
|ConfigurationServiceLeavingRunAsync|440083|
|ConfigurationServiceFailedToDeleteAsset|440084|
|ConfigurationServiceFailedToFindAsset|440085|
|ConfigurationServiceFailedToDeleteAssetType|440086|
|ConfigurationServiceFailedToFindAssetType|440087|
|ConfigurationServiceFailedToDeleteStream|440088|
|ConfigurationServiceFailedToFindStream|440089|
|ConfigurationServiceFailedToDeleteStreamType|440090|
|ConfigurationServiceFailedToFindStreamType|440091|
|ConfigurationServiceFailedToUpdateStreamTypeACL|440092|
|ResponseInProgressSkipWebExceptionMiddleware|450000|
|ExceptionHandledByWebExceptionMiddleware|450001|
|WebExceptionMiddlewareReceivedException|450002|
|ExceptionStartingProcessOfProvisioningResourcesForAgent|450003|
|ExceptionStartingAgentDeletion|450004|
|ExceptionGettingProvisioningStatusForAgent|450005|
|ExceptionClearingProvisioningStatusForAgent|450006|
|ErrorCreatingResourcesForAgent|450007|
|CreateCloudResourcesForAgentCompleted|450008|
|DeleteCloudResourcesForAgentCompleted|450009|
|UnexpectedErrorDeletingCloudResourcesForAgent|450010|
|FoundOrCreatedPIToOcsSdsTypes|450011|
|EventHubNamespaceAlreadyExistsInAzure|450012|
|CreatedEventHubNamespace|450013|
|EventHubNamespaceAlreadyDoesNotExistInAzure|450014|
|CreatedEventHub|450015|
|EventHubNamespaceIsNotAccessible|450016|
|CreatedDataService|450017|
|DataServiceAlreadyExists|450018|
|DataServiceForDeletionWasNotFound|450019|
|DataServiceDeletionWasCanceled|450020|
|DeletedDataService|450021|
|SdsTypeNotFound|450022|
|ErrorCreatingOrUpdatingSdsType|450023|
|ManagementServiceConstructed|450024|
|ExceptionCreatingManagementService|450025|
|ManagementServiceBeganRunAsync|450026|
|ManagementServiceShuttingDownDueToUnhandledException|450027|
|ManagementServiceLeavingRunAsync|450028|
|ManagementServiceClosing|450029|
|MissingEventHub|450030|
|MissingEventHubNamespace|450031|
|ExceptionVerifyingAgentResourcesExists|450032|
|ExceptionVerifyingAgentResourcesDeleted|450033|
|AzureSubscriptionFullForEHNamespaces|450034|
|EHNamespaceCreationFailed|450035|
|SuccessfulEHNamespaceCleanup|450036|
|BeginAgentResourceCreateVerification|450037|
|BeginAgentResourceDeleteVerification|450038|
|BeginTypeCreateVerification|450039|
|BeginEventHubNamespaceCreateVerification|450040|
|BeginEventHubCreateVerification|450041|
|BeginDataServiceCreateVerification|450042|
|BeginDataServiceDeleteVerification|450043|
|BeginEventHubNamespaceDeleteVerification|450044|
|ManagementServiceAborting|450045|
|ManagementServiceStartingKestrel|450046|
|BeginStreamsServiceCreateVerification|450047|
|CreatedStreamsService|450048|
|StreamsServiceAlreadyExists|450049|
|BeginStreamsServiceDeleteVerification|450050|
|StreamsServiceForDeletionWasNotFound|450051|
|StreamsServiceDeletionWasCanceled|450052|
|DeletedStreamsService|450053|
|BeginAssetsServiceCreateVerification|450054|
|CreatedAssetsService|450055|
|AssetsServiceAlreadyExists|450056|
|BeginAssetsServiceDeleteVerification|450057|
|AssetsServiceForDeletionWasNotFound|450058|
|AssetsServiceDeletionWasCanceled|450059|
|DeletedAssetsService|450060|
|RetrievingTransferMetrics|450061|
|UpdatingStreamsTransferMetrics|450062|
|UpdatingAssetsTransferMetrics|450063|
|ProvisioningMissingResources|450064|
|FailedToGetNamespaceLockDuringProvisioning|450065|
|ProvisioningSynchronizerExiting|450066|
|ProvisioningSynchronizerUnexpectedException|450067|
|AssetsTransferSpeedMetric|450068|
|AssetBulkCreateRequest|450069|
|AssetCreationRequestReponseStatus|450070|
|AssetBulkUpdateRequest|450071|
|AssetUpdateRequestReponseStatus|450072|
|AssetDeleteTransferSpeedMetric|450073|
|RetrievedSqlServer|460001|
|DatabaseAlreadyExists|460002|
|ErrorCreatingDatabase|460003|
|ErrorRetrievingDatabase|460004|
|DatabaseToBeDeletedNotFound|460005|
|ConfigServiceTerminatingDueToMissingDatabase|460006|
|UpgradingDatabase|460007|
|UpgradedDatabase|460008|
|ErrorUpgradingDatabase|460009|
|TransportMessageTooLargeForEventHub|460010|
|TransportMessageSizeMismatch|460011|
|RetryHandlerRetrying|460012|
|BeginProvisioningSqlDatabase|460013|
|SqlDatabaseProvisioningComplete|460014|
|ErroneousForbiddenExceptionReceivedForIncorrectSqlBackupSettings|460015|
|RetryableErrorCreatingSqlDatabase|460016|
|ForbiddenExceptionReceivedForCorrectSqlBackupSettings|460017|
|ProvisioningAllAgentsResources|460018|
|FailedProvisioningAllAgentsResources|460019|
|FailedProvisioningAgentsResources|460020|
|ErrorCreatingOrUpdatingElasticPool|460021|
|ErrorRetrievingElasticPool|460022|
|ErrorDeletingElasticPool|460023|
|ErrorUpdatingDatabase|460024|
|ErrorPoolingDatabases|460025|
|ElasticPoolAlreadyExists|460026|
|BeginProvisioningElasticPool|460027|
|ElasticPoolProvisioningComplete|460028|
|DeletedElasticPool|460029|
|BeginElasticPoolRebalancing|460030|
|ElasticPoolRebalancingComplete|460031|
|BeginElasticPoolAssignment|460032|
|CompletedElasticPoolAssignment|460033|
|AllDatabasesArePooled|460034|
|FoundUnpooledDatabases|460035|
|PointTrace|460036|
|RetryHandlerTotalDurationTimeout|460037|
|RetryHandlerMultiStatusDurationTimeout|460038|
|ErrorGettingRolesForTrustee|460039|
|RetryHandlerChildErrorsInMultiStatusResponse|460040|
|FailedToDeserializeMultiStatusContent|460041|

---

### DetailedStreamCreationStatus

<a id="schemadetailedstreamcreationstatus"></a>
<a id="schema_DetailedStreamCreationStatus"></a>
<a id="tocSdetailedstreamcreationstatus"></a>
<a id="tocsdetailedstreamcreationstatus"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TransferId|guid|false|false|None|
|Status|[SimpleTaskStatus](#schemasimpletaskstatus)|false|false|None|
|TotalPointStreamsExpected|int64|false|false|None|
|VerifiedPointStreamsCreated|int64|false|false|None|
|LastUpdateAttempt|date-time|false|false|None|
|LastSuccessfulUpdate|date-time|false|false|None|
|LastMessage|[CreationStatusType](#schemacreationstatustype)|false|false|None|

```json
{
  "TransferId": "string",
  "Status": 0,
  "TotalPointStreamsExpected": 0,
  "VerifiedPointStreamsCreated": 0,
  "LastUpdateAttempt": "2019-08-24T14:15:22Z",
  "LastSuccessfulUpdate": "2019-08-24T14:15:22Z",
  "LastMessage": 0
}

```

---

### SimpleTaskStatus

<a id="schemasimpletaskstatus"></a>
<a id="schema_SimpleTaskStatus"></a>
<a id="tocSsimpletaskstatus"></a>
<a id="tocssimpletaskstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Done|0|
|Working|1|
|Failed|2|
|NotStartedYet|3|
|PIPointTypeChangeDetected|100|

---

### CreationStatusType

<a id="schemacreationstatustype"></a>
<a id="schema_CreationStatusType"></a>
<a id="tocScreationstatustype"></a>
<a id="tocscreationstatustype"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Unknown|0|
|Failed|1|
|Success|2|
|PointTypeMismatch|3|

---

### HistoricalTransferProgress

<a id="schemahistoricaltransferprogress"></a>
<a id="schema_HistoricalTransferProgress"></a>
<a id="tocShistoricaltransferprogress"></a>
<a id="tocshistoricaltransferprogress"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TransferId|guid|false|false|None|
|TotalArchives|int32|false|false|None|
|CurrentArchive|int32|false|false|None|
|TotalPointsInArchive|int32|false|false|None|
|TransferredPointsForArchive|int32|false|false|None|

```json
{
  "TransferId": "string",
  "TotalArchives": 0,
  "CurrentArchive": 0,
  "TotalPointsInArchive": 0,
  "TransferredPointsForArchive": 0
}

```

---

### AFIndexProgress

<a id="schemaafindexprogress"></a>
<a id="schema_AFIndexProgress"></a>
<a id="tocSafindexprogress"></a>
<a id="tocsafindexprogress"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|NotStarted|0|
|AFIndexInProgress|1|
|AFIndexingFailed|2|
|AFIndexingSucceeded|3|
|Restarting|4|

---

### PIPointAttributeCacheProgress

<a id="schemapipointattributecacheprogress"></a>
<a id="schema_PIPointAttributeCacheProgress"></a>
<a id="tocSpipointattributecacheprogress"></a>
<a id="tocspipointattributecacheprogress"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|NotStarted|0|
|PIPointIndexInProgress|1|
|PIPointIndexingFailed|2|
|PIPointIndexingSucceeded|3|
|Restarting|4|

---

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|
|DynamicProperties|object|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "DynamicProperties": {
    "property1": null,
    "property2": null
  },
  "property1": null,
  "property2": null
}

```

---

### CapabilityState

<a id="schemacapabilitystate"></a>
<a id="schema_CapabilityState"></a>
<a id="tocScapabilitystate"></a>
<a id="tocscapabilitystate"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Enabled|boolean|false|false|None|

```json
{
  "Enabled": true
}

```

---

### Capability

<a id="schemacapability"></a>
<a id="schema_Capability"></a>
<a id="tocScapability"></a>
<a id="tocscapability"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|id|string|false|true|None|
|ver|int32|false|false|None|
|en|boolean|false|false|None|

```json
{
  "id": "string",
  "ver": 0,
  "en": true
}

```

---

