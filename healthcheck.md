## Healthcheck

The example below is for users who choose nutrition. A complete list of possible event labels can be found [here]

**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
healthcheck|started healthcheck|nutrition onboarding *or* nutrition twin *or* nutrition retake|user starts healthcheck option from welcome screen *or* digital twin *or* by retaking a completed assessment
healthcheck|completed healthcheck|nutrition onboarding *or* nutrition twin *or* nutrition retake|user completes healthcheck option from welcome screen *or* digital twin *or* by retaking a completed assessment


#### Healthcheck events - JS
##### started healthcheck onboarding
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'started healthcheck',
    label: 'nutrition onboarding'
  }}
  );
```
##### completed healthcheck onboarding
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'completed healthcheck',
    label: 'nutrition onboarding'
  }}
  );
```
##### started healthcheck twin
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'started healthcheck',
    label: 'nutrition twin'
  }}
  );
  ```
  ##### completed healthcheck twin
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'completed healthcheck',
    label: 'nutrition twin'
  }}
  );
  ```
  ##### start retake healthcheck
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'start healthcheck',
    label: 'nutrition retake'
  }}
  );
  ```
   ##### complete retake healthcheck
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'complete healthcheck',
    label: 'nutrition retake'
  }}
  );
