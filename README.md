# BERTA
a workflow engine that will test events as called for (qusi real time)
Bundles - bundles consist of rules
Rules - rules consist of tests and actions
Tests - tests consist of weighted events
Actions - actions can update bundles to make them active or to deactivate them; actions can also call processes before or after those updates.
Events - events call functions that examine the real world.


at the end of the test the sum of the weighted events will be used in comparison to that rules action threashold numbers.
a rule is said to fire if one of its actions threashold number is exceeded 
if a rule fires:
1 - all of the functions-before are collected to the functions queue
2- all 
table format in miller

Bundle --< bundle/rules >-- rules ;;

bundle/rules --> ruleQueue ;;

rules --< rule/tests >-- tests ;;

rule/tests --> testQueue ;;
rules --< threasholdActions >-- actions ;;
tests --< test/events >-- events ;;
test/events --> eventQueue ;;
events --- Eventfunctions ;;
rules --< actions ;;
actions --< bundle+ ;;
bundle+ --> bundle+queue ;;
actions --< bundle- ;;
bundle- --> bundle-queue ;;
actions --< functions-before >-- functions ;;
functions-before --> functionsQueue ;;
actions --< functions-after >-- functions ;;
functions-after --> functionsQueue ;;
sequenceer ;;
bundle ==//fn1//==> bundle-que ;;
rule ==//fn2//==> rule-que ;;
test ==//fn3//==> test-que ;;
event ==//fn4//==> event-que ;;
pdxn --< pdxGraph ;;
pdx.main ==> eventFunctions ; processFunctions /* sub sets */

bundle ((BID(desc, coldSW, ReadySW) ;;
bundle/rules((BID,RID)) ;;
rules((RID)) ;;
..

