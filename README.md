# BERTA
<br/>a workflow engine that will test events as called for (qusi real time). Which consists of the following objects:

<br/>Bundles - bundles consist of rules

<br/>Events - events call functions that examine the real world.

<br/>Rules - rules consist of tests and actions.

<br/>Tests - tests consist of weighted events

<br/>Actions - actions can update bundles to make them active or to deactivate them; actions can also call processes before or after those updates.

at the end of the test the sum of the weighted events will be used in comparison to that rules action threashold numbers.
a rule is said to fire if one of its actions threashold number is exceeded 
if a rule fires:<br />
<br/>1 - all of the functions-before are collected to the functions queue
<br/>2- all 
<br/><br/>table format in miller

<br/>Bundle --< bundle/rules >-- rules ;;

<br/>bundle/rules --> ruleQueue ;;

<br/>rules --< rule/tests >-- tests ;;

<br/>rule/tests --> testQueue ;;
<br/>rules --< threasholdActions >-- actions ;;
<br/>tests --< test/events >-- events ;;
<br/>test/events --> eventQueue ;;
<br/>events --- Eventfunctions ;;
<br/>rules --< actions ;;
<br/>actions --< bundle+ ;;
<br/>bundle+ --> bundle+queue ;;
<br/>actions --< bundle- ;;
<br/>bundle- --> bundle-queue ;;
<br/>actions --< functions-before >-- functions ;;
<br/>functions-before --> functionsQueue ;;
<br/>actions --< functions-after >-- functions ;;
<br/>functions-after --> functionsQueue ;;
<br/><br/>sequenceer ;;
<br/>bundle ==//fn1//==> bundle-que ;;
<br/>rule ==//fn2//==> rule-que ;;
<br/>test ==//fn3//==> test-que ;;
<br/>event ==//fn4//==> event-que ;;
<br/>pdxn --< pdxGraph ;;
<br/>pdx.main ==> eventFunctions ; processFunctions /* sub sets */

<br/>TABLE bundle ((BID(desc, coldSW, ReadySW) ;;
<br/>TABLE bundle/rules((BID,RID)) ;;
<br/>TABLE rules((RID)) ;;
..

