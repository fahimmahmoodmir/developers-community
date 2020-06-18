Add a domain - SEE ACTUAL TOPIC & UPDATE
Add an intent - SEE ACTUAL TOPIC & UPDATE


### Configure domain settings

**To configure domain settings**

1. Open the domain.
2. Click Domain Settings in the upper-left corner.
3. Specify the following:
    * **Domain Name**: Enter a name. Use a standard naming convention to make sorting and finding domains easier.
    * **Add Intents and Entities**: You can select to add these manually or import them via a CSV file or Google sheet. If you import them via a CSV file, the operation is additive, i.e., the intents and entities are appended to the existing ones.
    * **NLU Provider**: Read-only. The provider of the NLU engine can’t be changed after you create the domain.
    * **Language**: The language of the domain.
    * **Domain ID**: Read-only. This is a unique identifier that’s generated by the system. In some scenarios (e.g., API calls), you might need to reference the domain ID. Here’s where you can find it.
    * **Has Intent Analyzer**: Read-only. Indicates whether [Intent Analyzer](intent-analyzer-overview.html) has been enabled for intents.
    * **Analyze Masked Data**:
    * **Domain Account**: Select the account under which the domain should exist. This is used to move domains from one account (org) to another.
    * **Enable Key Phrase Match**: Available only if the NLU engine used by the domain is LivePerson NLU v1. Select this to enable Key Phrase Matching. Once enabled, select the threshold to use. For more on Key Phrase matching, see farther below.
4. Click **Update Domain**.

#### Key Phrase Matching (LivePerson NLU v1 only)

Enable Key Phrase Match is a domain setting that’s only available in domains that use the LivePerson NLU v1 engine. It’s designed to improve the NLU matching by adding another “layer” of matching during intent prediction.

A key phrase is a critical noun or verb. If you enable Key Phrase Matching for the domain, you can specify a collection of key phrases for each intent. During intent prediction, the key phrases are evaluated after the training phrases. If the key phrases are found in the user’s utterance, the NLU score for the intent is boosted to GOOD even if the utterance doesn’t match any of the intent’s training phrases.

Here's a test example without Key Phrase Matching enabled:

<img class="fancyimage" style="width:500px" src="img/ConvoBuilder/ib_keyPhraseMatch1.png">  

And here's a test example with Key Phrase Matching enabled: 

<img class="fancyimage" style="width:500px" src="img/ConvoBuilder/ib_keyPhraseMatch2.png">

Key Phrase Matching uses a threshold that you must specify when you enable the domain setting. As an example, if you set the threshold to 2, then if 2 of the intent’s key phrases are found in the consumer’s utterance, the intent is considered a match.

<img class="fancyimage" style="width:500px" src="img/ConvoBuilder/ib_keyPhraseMatch3.png">

Key Phrase Matching can be helpful when you know there are specific words that directly correlate with an intent because it boosts the score when appropriate. For example, with the LivePerson NLU v1 engine, the NLU score is penalized when the consumer’s utterance is too long when compared to the training phrases. Let’s say the consumer says, “The weather is nice, but I forgot my password, and now my whole day is ruined as a result of my forgetfulness. Please help. I don't know what to do.” In your domain, you have a “Forgot password” intent, but it doesn’t yield a match because of the utterance’s length. Without key phrase matching, there isn’t a match. However, if you know that any time the consumer says something that contains the words “forgot” and “password” that it’s related to the “Forgot password” intent, you can add those words as key phrases and boost the score to GOOD when they are found in the utterance. (Since the intent is matched, this also means it can be in contention for disambiguation if disambiguation used.)


### Add an entity

**To add an entity**

1. Open the domain.
2. In the upper-left corner, click **Entities**.
3. Click **Add Entity** in the upper-right corner.
4. Specify the following:
    * **Entity name**: Enter the name of the entity using alphanumeric characters (no special characters). Consider using all capital letters and underscores (instead of spaces) as a convention; this makes the entities readily visible when they are used in intents and knowledge bases.
    * **Entity values**: Enter each entity value, pressing Enter after each one.
5. Click **Add Entity** in the lower-right corner.


### Delete a domain

Deleting a domain is a non-recoverable action, so be certain about doing so before taking this action.

{: .important}
Ensure the domain isn't being used by any bots or knowledge bases before you delete it. Also, consider downloading the domain for backup purposes before you delete it.

**To delete a domain**

1. Open the domain.
2. In the upper-left corner, click **Domain Settings**.
3. Click **More Settings**, scroll down to the Delete Domain section, and click <img style="width:25px" src="img/ConvoBuilder/icon_delete.png"> (Delete icon).
4. In the confirmation dialog, click **Yes**.


### Delete an intent

Deleting an intent is a non-recoverable action, so be certain about doing so before taking this action.

{: .important}
Ensure the intent isn't being used by any bots or knowledge bases before you delete it.

**To delete an intent**

1. Open the domain.
    By default, the Intents page is displayed.
2. In the left panel, select the intent.
3. Click <img style="width:25px" src="img/ConvoBuilder/icon_ellipsis_vertical.png"> (3-dot icon), and select **Delete**.
4. In the confirmation dialog, click **Yes**.
5. If the domain is using LivePerson NLU v2 or a 3rd-party NLU engine, train the domain so that the deletion is reflected in a new model version.


### Delete an entity

Deleting an entity is a non-recoverable action, so be certain about doing so before taking this action.

{: .important}
Ensure the entity isn't being used in any intents before you delete it.

**To delete an entity**

1. Open the domain.
2. In the upper-left corner, click **Entities**.
3. In the left panel, select the entity.
4. Click <img style="width:25px" src="img/ConvoBuilder/icon_ellipsis_vertical.png"> (3-dot icon), and select **Delete**.
5. In the confirmation dialog, click **Yes**.
6. If the domain is using LivePerson NLU v2 or a 3rd-party NLU engine, train the domain so that the deletion is reflected in a new model version.


### Download a domain

Download of a domain creates a ZIP file that contains 2 CSV files, one for the intents and the other the entities.

You might need to download a domain for a few reasons:

* You want to create a copy of the domain by downloading it and then adding a new domain using the CSV as the import file.
* You want to move or copy the domain to another environment.
* You want an extra measure of back-up, so you plan to archive the CSV file for safekeeping.

**To download a domain**

1. Open the domain.
2. In the upper-left corner, click **Domain Settings**.
3. Click **More Settings**, scroll down to the **Export Intents and Entities** section, and click <img style="width:25px" src="img/ConvoBuilder/icon_ib_download.png"> (Download icon).
4. Follow the browser prompts to access and save the ZIP file to a location of your choice.