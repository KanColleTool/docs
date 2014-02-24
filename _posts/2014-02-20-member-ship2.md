---
category: get_member
path: '/kcsapi/api_get_master/ship2'
title: 'Get list of your ships'
type: 'POST'

layout: nil
---

Returns information about all of your shipgirls.

### Request

* Standard parameters

```
{
	api_verno: 1,
	api_token: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
}
```

### Response

Return all the member's shipgirls and fleets

```
{
	api_result: 1,
	api_result_msg: 成功,
	api_data: [
		{
			api_id: int (local ID for your deck),
			api_sortno: int (The number on the card),
			api_ship_id: int (ID of the ship type),
			api_lv: int (Ship level),
			api_exp: [ ??? ] (An array of values),
			api_nowhp: int (Current hp),
			api_maxhp: int (Max hp),
			api_leng: int (Range),
			api_slot: [ int... ] (Equipped items),
			api_onslot: [ int... ] (Max planes in each slot?),
			api_kyouka: [ int... ] (???),
			api_backs: int (Rarity),
			api_fuel: int (Current fuel),
			api_bull: int (Current bullets),
			api_slotnum: int (Number of equipment slots),
			api_ndock_time: int (Seconds until repair completion),
			api_ndock_item: [ int (Steel to repair), int (Fuel to repair) ],
			api_srate: int (???),
			api_cond: int (Condition),
			api_karyoku: [ int (Current firepower), int (Max firepower) ],
			api_raisou: [ int (Current torpedo power), int (Max torpedo power) ],
			api_taiku: [ int (Current anti-air), int (Max anti-air) ],
			api_soukou: [ int (Current armor), int (Max armor) ],
			api_kaihi: [ int (Current evasion), int (Max evasion) ],
			api_taisen: [ int (Current anti-sub), int (Max anti-sub) ],
			api_sakuteki: [ int (Current line of sight), int (Max line of sight) ],
			api_lucky: [ int (Current luck), int (Max luck) ],
			api_locked: int (Heart lock)
		}
		...
	],
	api_data_deck: [
		{
			api_member_id: int (The member's ID),
			api_id: int (The fleet ID),
			api_name: string (The fleet name),
			api_name_id: "" (Always seems to be empty),
			api_mission: [
				int (Expedition page),
				int (Expedition number),
				int (Completion timestamp),
				int (???)
			],
			api_flagship: "0" (Always seems to be "0"),
			api_ship: [ int... ] (Ship ID's)
		}
		...
	]
}
```
