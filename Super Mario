:local n11 63,66;
:local n12 64,67;
:local n21 71,69,68,69,68,66,68,64,66,63;
:local n22 64,63;

:local n11 ($n11,$n11);
:local n12 ($n12,$n12);
:local n1 ($n11,$n11,$n12,$n12);
:local n2 ($n21,$n22,$n22,$n22);
:local notes ($n1,$n1,$n2,$n2);
  
:local ticks 2;
:local speed 55ms;
:local stacc 5ms;
# Transposition
:local transpose -48;
# ==============================
# Don't change this:
:local frqtab 8372,8869,9397,9956,10548,11175,11839,12543,13288,14080,14916,15804;
:local n0; :local n;
:local d0; :local d;
:local l;
:local midi;
:local i;
:local octa;
:local frq;
:for i from=0 to= ([:len $notes]-1) do={
:set midi [:pick $notes $i];
:set midi ($midi + $transpose);
:set octa 0;
:while ( $midi < 60) do={:set midi ($midi + 12); :set octa ($octa + 1   ); };
:set midi ($midi - (12 * ($midi /12)));
:set frq [:tonum [:pick $frqtab $midi]];
:set frq ($frq>>($octa));
:set d0 $ticks;
:set d ($d0 * $speed );
:set l ($d0 * ($speed - $stacc));
:beep fr=$frq le=$l;
:delay $d;
:set midi 59;
:set midi ($midi + $transpose);
:set octa 0;
:while ( $midi < 60) do={:set midi ($midi + 12); :set octa ($octa + 1   ); };
:set midi ($midi - (12 * ($midi /12)));
:set frq [:tonum [:pick $frqtab $midi]];
:set frq ($frq>>($octa));
:set d0 $ticks;
:set d ($d0 * $speed );
:set l ($d0 * ($speed - $stacc));
:beep fr=$frq le=$l;
:delay $d;
}
