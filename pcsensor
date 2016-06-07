#!/bin/bash

# Where is pcsensor located?
PCSENSOR="/usr/local/bin/pcsensor"

if [ ! -e ${PCSENSOR} ]; then
	echo "pcsensor executable not found" >&2
	exit -1
fi

if [ "${1}" = "config" ]; then
	echo "graph_title TEMPer USB Thermometer"
	echo "graph_scale no"
	echo "graph_vlabel Celsius"
	echo "graph_category sensors"
	echo "graph_info This graph shows the temperature reported by the first attached TEMPer2 USB Thermometer"
	
	echo "temp1.label temperature1"
	echo "temp1.type GAUGE"
        echo "temp2.label temperature2"
        echo "temp2.type GAUGE"
else
	TEMP1=`${PCSENSOR} -cm | head -n 1 | tail -n 1`
	if [[ $? != 0 ]]; then
		sleep 2
		TEMP1=`${PCSENSOR} -cm | head -n 1 | tail -n 1`
		if [[ $? != 0 ]]; then
			sleep 6
			TEMP1=`${PCSENSOR} -cm | head -n 1 | tail -n 1`
		fi
	fi
	echo "temp1.value $TEMP1"

	TEMP2=`${PCSENSOR} -cm | head -n 2 | tail -n 1`
        if [[ $? != 0 ]]; then
                sleep 2
                TEMP2=`${PCSENSOR} -cm | head -n 2 | tail -n 1`
                if [[ $? != 0 ]]; then
                        sleep 6
                        TEMP2=`${PCSENSOR} -cm | head -n 2 | tail -n 1`
                fi
        fi
	echo "temp2.value $TEMP2"
fi
