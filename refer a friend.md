## Refer Friend

**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
refer a friend|accepted referral|'went to', 'came back'|user who has been referred goes to or comes back from the referral modal
refer a friend|referred friend|'went to', 'came back'|user who wants to refer goes to or comes back from the referral modal


#### Refer a friend events - JS
##### referred friend
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
##### referred friend return
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
##### accepted referral
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
##### accepted referral return
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
