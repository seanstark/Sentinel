# Joshua - Cyberiskvision

Joshua Cyberiskvision provides two main use cases: Get Indicators and Alert Enrichment.

# Get Indicators from Joshua

These playbooks automate the ingest of Joshua Cyberiskvision threat indicators into the ThreatIntelligenceIndicator table of a Microsoft Sentinel workspace.

Note: You must deploy the "Joshua-Import-To-Sentinel" playbook before deploying the "Joshua-Indicators-Processor" playbooks.

Joshua-Import-To-Sentinel performs the following steps:
 - Begins with a Batch Messages trigger to receive indicators sent by Joshua-Indicators-Processors
 - Submits each batch of indicators to Microsoft Sentinel using the Microsoft Graph Security Logic App connector

Joshua-Import-To-Sentinel.json
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Import-To-Sentinel%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Indicators-Processors playbooks performs the following steps: 
 - Triggered on a defined schedule
 - Reads the indicators from Joshua Cyberiskvision
 - Transforms the indicators to the appropriate tiIndicator JSON format
 - Uses the Batch action to send the indicators to the "Joshua-Import-To-Sentinel"

Joshua-Indicators-Processor-IP
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Indicators-Processor-IP%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Indicators-Processor-URL
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Indicators-Processor-URL%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Indicators-Processor-DOMAIN
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Indicators-Processor-DOMAIN%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Indicators-Processor-FILE
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Indicators-Processor-FILE%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Indicators-Processor-EMAIL
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Indicators-Processor-EMAIL%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

# Joshua Alerts Enrichment

These playbooks use the Joshua Cyberiskvision threat intelligence to automatically enrich incidents generated by Microsoft Sentinel.
From the analyst perspective, it is important that the alert contains essential information and therefore the ability to include custom details in the alert will improve the efficiency of investigation.
Through this integration, the analyst can enrich incidents with further information.
Enriched data will be added in Microsoft Sentinel incident comments.

Joshua-Intel-Enrichment-IP.json
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Intel-Enrichment-IP%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Intel-Enrichment-URL.json
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Intel-Enrichment-URL%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

Joshua-Intel-Enrichment-FILE.json
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcyberiskvision%2FAzure-Sentinel%2Fmaster%2FSolutions%2FJoshua-Cyberiskvision%2FPlaybooks%2FJoshua-Intel-Enrichment-FILE%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>