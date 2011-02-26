#!/bin/sh
SYNC=$(qlop -sC | awk 'END{gsub(/>>>.*/,""); print}' | xargs -i date -d "{}" '+%s')

if [ "$1" -a "$1" = "days" ];
then
	DAYS=$(( ($(date +%s)-SYNC) / (24*3600) ))
	if [ $DAYS = 1 ]; then
		echo "$DAYS day ago"
	else
		echo "$DAYS days ago"
	fi
else
	date -ud@$SYNC "+%a %d %b %Y"
	fi
