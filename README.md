# BERTA
a workflow engine that will test events as called for (qusi real time)
bundles consist of rules
rules consist of tests
tests consist of weighted events
events call functions that will examine the real world
at the end of the test the sum of the weighted events will be used in comparison to that rules threashold numbers
a rule is said to fire if some threashold number is exceeded (in the case of multiple threasholds the max number reached)
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

bundle ((BID(desc, coldSW, ReadySW) ;;
bundle/rules((BID,RID)) ;;
rules((RID)) ;;
..

