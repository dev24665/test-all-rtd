Important:
--------------
PDC studies can have multiple versions. While each version of study will have a UUID based unique study id, the PDC study ID (e.g., PDC000121) will always remain the same. By default, all the APIs will return the data related to the latest version. The APIs show the following behavior,

In order to understand the available versions, we strongly recommend you to first visit PDC portal or call the studyCatalog API. The studyCatalog API will provide a list of studies along with all their versions, version number and version status.
When calling an API with PDC study ID (e.g., PDC000121) as input parameter, it will return data for the latest version.
When calling an API with UUID based study ID (e.g., be2883cb-57b8-11e8-b07a-00a098d917f8) as input parameter, it will return data for the specific version.
