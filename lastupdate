#!/usr/bin/awk -f
BEGIN {

	while (getline < "/var/log/emerge.log")
		if ($2 == "***" && $3 == "emerge" && $0 ~ "--update" && $0 ~ "world") {
			tmp = $1;
			getline < "/var/log/emerge.log";
			if($2 == ">>>")
				last = tmp;
		}

	gsub(":", "", last);

	if(ARGV[1] == "days") {
		days = int((systime()-last)/86400)
		print days, "day" (days == 1 ? "" : "s") " ago"
	}
	else
		print strftime("%c", last)
}
