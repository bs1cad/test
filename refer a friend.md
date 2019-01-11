## Refer Friend

**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
refer a friend|accepted referral|'went to', 'came back'|user who has been referred goes to or comes back from the referral modal
refer a friend|referred friend|'went to', 'came back'|user who wants to refer goes to or comes back from the referral modal


#### Refer a friend events - JS
##### invite friend
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'referred friend',
    label: 'went to'
  }}
  );
```
##### invite friend return
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'referred friend',
    label: 'came back'
  }}
  );
```
##### referred
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'accepted referral',
    label: 'went to'
  }}
  );
```
##### referred return
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'accepted referral',
    label: 'came back'
  }}
  );
```
