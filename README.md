Codesys 2.3
Wsad dla sterownika 750-880. 2 moduły wejściowe 750-430 oraz 13 modułów przekaźnikowych 750-513. 

Zaimplementowane bibloteki SysLibRtc, Visu_Scheduler, oscat_building, oscat_basic, bulding_common, sysLibFile, mod_com, 

3 wizualizacje:
- pierwsza do obsługi sterowania roletami, sterowanie indywidualne góra/dół/ zaciemnienie, oraz sterowanie centralne otwieranie/zamykanie wszystkiego wraz z wyborem, które rolety mają być sterowane.
- druga z podwójnych harmonogramem tygodniowym
- trzecia ustawienia pozycji rolet, ustawienia zaciemnienia, ustawienie czasu góra/dół i czas zasilania rolety, wszystko konfigurowane z panelu wizualizacji.

(*obsługa zegaru rtc, ramek modbus tcp*)
  VIS_OUT1 AT %MX294.0: BOOL;
	VIS_OUT_ALL_DN AT %MX327.0: BOOL;

(*zerowanie zmiennej modbus po wykonaniu pracy*)
  IF VIS_OUT_ALL_DN THEN
  VIS_OUT_ALL_DN := 0;
  END_IF

(*Przyciski double*)
Double_IN1( xSwitch := IN1 );

(* ---------- przyciski KRÓTKI / DLUGI --------------- *)
LongShort_IN1( xSwitch := IN1 );

