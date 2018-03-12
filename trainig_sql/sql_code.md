select
 play_type,
 count(play_type) as count_play_type
 count(distinct user_id) as uu,
 count(1) as count_one

from    
 `warm-calculus-736.liverpool_tableau.fav_imp_play_logs`

where
_PARTITIONTIME >= "2018-02-28 00:00:00" AND _PARTITIONTIME < "2018-03-08 00:00:00"  
and
fav_at between "2018-03-01" and "2018-03-07"
and
play_type in ('discovery', 'trending_awa')
and
type='fav_track'
and
group by play_type
