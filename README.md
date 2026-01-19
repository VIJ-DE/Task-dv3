# Task-dv3
Networking basis for devops 
#!/bin/bash

REPORT="network_report.txt"

echo "===============================" > $REPORT
echo " NETWORK ANALYSIS REPORT" >> $REPORT
echo " Date: $(date)" >> $REPORT
echo "===============================" >> $REPORT

echo -e "\n1. SYSTEM IP DETAILS" >> $REPORT
ip a >> $REPORT

echo -e "\n2. DEFAULT GATEWAY" >> $REPORT
ip route >> $REPORT

echo -e "\n3. PING TEST (Google DNS - 8.8.8.8)" >> $REPORT
ping -c 4 8.8.8.8 >> $REPORT

echo -e "\n4. DNS RESOLUTION TEST (google.com)" >> $REPORT
nslookup google.com >> $REPORT

echo -e "\n5. DNS RESOLUTION USING DIG" >> $REPORT
dig google.com >> $REPORT

echo -e "\n6. OPEN PORTS AND SERVICES (ss)" >> $REPORT
ss -tuln >> $REPORT

echo -e "\n7. NETWORK PATH TRACE (traceroute)" >> $REPORT
traceroute google.com >> $REPORT

echo -e "\n===============================" >> $REPORT
echo " REPORT COMPLETED SUCCESSFULLY" >> $REPORT
echo "===============================" >> $REPORT

echo "Network analysis completed. Report saved as $REPORT"
