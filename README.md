# bi_controller
Intallare prima il pacchetto rotors presente su git-hub :" https://github.com/ethz-asl/rotors_simulator "<br>
Sostituire in: rotors_simulator/rotors_control/src/nodes  i "file lee_position_controller_node.cpp" e "lee_position_controller_node.h"<br>
Sostituire in: rotors_simulator/rotors_gazebo/src il file: "hovering_example.cpp" <br>
Sostituire in: /rotors_simulator/rotors_control/src/library il file: "lee_position_controller.cpp" <br>
Sostituire in : rotors_simulator/rotors_control/include/rotors_control il file : "lee_position_controller.h"<br>
Aggiungere nella cartella SRC le seguenti cartelle:bi_controller,control_layer,estimator,neural_net_py e successivamente compilare <br>
Aggiungere la cartella Neural_net_v5 e Neural_net_v4 nella cartella Home del prorpio computer.<br>
Si può scegliere se utilizzare Neural_net_v5 che presenta la rottura di tutti e 4 i motori oppure Neural_net_v4 che presenta la rottura solo del motore 2-4 per cambiare la rete neurale basta andare all'interno del file "listener.py" presente nella cartella neural_net_py e commentare la riga 34 e de-commentare la riga 33.<br>
Nel caso in cui si vuole testare la rete neurale con la rottura di un qualsiasi motore, all'interno del file listener.py commentare dalla riga 40 alla 45.<br>
Per eseguire tutto il programma bisogna utilizzare la seguente sequenza all'interno del terminale:<br>
1."$roslaunch rotors_gazebo mav_with_waypoint_publisher.launch mav_name:=hummingbird world_name:=basic"<br>
Aprire un nuovo terminale:<br>
2."$rosrun control_layer control_layer"<br>
Aprire un nuovo terminale:<br>
3."$rosrun stimatore stimatore"<br>
Aprire un nuovo terminale:<br>
4."$rosrun neural_net_py listener.py"<br>
Aprire un nuovo terminale:<br>
5."$roslaunch bi_controller bi_controller.launch "<br>
N.B: Nel caso in cui non si voglia far passare il drone per determinati punti di via ma lasciarlo in hovering invce di usare il comando 1. utilizzare il comando 1.bis <br>
1.bis"$roslaunch rotors_gazebo mav_hovering_example.launch mav_name:=hummingbird world_name:=basic"<br>
N.B.2: Se quando si avvia lo stimatore i valori della coppia,ovvero gli utili 3 valori (stima(4),stima(5),stima(6)) sono maggiori di e-19 riavviare lo stimatore.<br>
NB.3:Se quando si avvia il bi_controller la tau risulta più elevata di circa 20 allora riavviare il bi_controller.

