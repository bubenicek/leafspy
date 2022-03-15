# leafspy

Co je vidět na displeji auta (tzv. dash display)?
Vpravo grafický indikátor nabití baterky + indikátor stavu/zdraví baterky (State of health, SOH). Nabití baterky lze v číselné podobě zobrazit i uprostřed displeje (% v symbolu baterky). Indikátor stavu baterky má 12 dílků, ale nikde v menu displeje nezjistíte, jaký je vlastně aktuální stav SOH u konkrétního EV a kolik zbývá do zmiznutí prvního dílku baterky. Většina laiků si myslí, že když má stupnice 12 dílků, tak že 1 dílek má hodnotu 1/12 čili 8,33%, čili pokud ubyde 1 dílek, tak baterka má SOH 100 - 8,33 = 91,67%. To je ovšem omyl, první dílek zmizí, pokud má baterka po dobu delší než měsíc SOH menší než 85%. Stupnice totiž není lineární. Odkud to vím? Ze Spy a z jeho manuálu.

Vlevo na displeji je indikátor teploty baterky. Výrobce v manuálu uvádí, že rychlonabíjením se baterka nabije na 80% za cca 30 min, pokud je teplota baterky v rozmezí 6. a 7.segmentu. Pokud je baterka teplejší nebo studenější, tak to trvá déle, cca 30-90min. Jenže kolik je to ve stupních Celsia, resp. kolik zbývá do ideální teploty? Proč se někdy Leaf nabije z vysokých % SOC málo za dlouhou dobu a jindy z nízkých % SOC hodně za krátkou dobu? Na to odpoví Spy.

Uprostřed displeje se zobrazují využitelná % v symbolu baterky, ovšem jen do 6%. Pokud údaj klesne pod 6%, tak zmizí. Jak v tuto chvíli zjistíte, kolik zbývá využitelných % v baterce, jestli si můžete dovolit jet dál posledních pár km, nebo musíte hledat zásuvku? Na to odpoví Spy.

Spy ve verzi Pro má 5 obrazovek:
1.obrazovka
- Bat status (Ah) - dobré pro porovnání např. s BMW
- SOH (%) - zdraví baterky
- napětí baterky (V)
- Hx (%)
- odo (km) - počet najetých km
- QCs - počet rychlých nabíjení
- L1/L2s - počet pomalých nabíjení
- graf napětí na jednotlivých párech článků
Z této obrazovky jsou alespoň pro mě nejdůležitější údaje Hx a SOH. Hx je podle manuálu Spy nepřímo úměrný vnitřnímu odporu baterky, který je indikátorem stárnutí baterky - když vnitřní odpor baterky roste, Hx klesá (a obráceně). S poklesem Hx klesá i SOH čili zdraví baterky. SOH je s přesností na celá %, na tom se během jízdy vysledovat nic moc nedá. Mnohem zajímavější je proto Hx, který je s přesností na setiny %. V praxi jsem si ověřil, že když má baterka správnou teplotu (minimálně cca 22st.C nad teplotou okolí), tak vhodným stylem jízdy (jemné střídání plyn - rekuperace - plyn atd.) se dá docílit toho, že nejen že Hx neklesá, ale dokonce někdy i roste. Po vypnutí a zapnutí auta pak při překročení určitých hranic % Hx dojde k tomu, že se změní % SOH. Samostatnou kapitolou je dosahování optimální teploty baterky - toho se dá docílit buď rychlonabíjením, nebo rychlou jízdou např. po dálnici, nebo nejlépe kombinací obojího. Samozřejmě ani takto se zřejmě ve finále nedá oklamat fyzikální podstata - stárnutí baterky, ke kterému při ježdění nevyhnutelně dochází. Ovšem lze tak oddálit okamžik, kdy SOH poklesne pod 85% a po měsíci ubyde první dílek na indikátoru na displeji auta. U nás k tomu došlo při 130.000km, ale znám případy, kdy k tomu došlo i pod 100.000km. To může mimo jiné mít zásadní vliv např. na cenu při prodeji EV apod. Celkový přínos vidím v tom, že se řidič EV naučí nabíjet a jezdit způsobem, který zpomaluje stárnutí baterky.

2.obrazovka
V aktuální verzi obsahuje 5 podobrazovek, z nichž nejdůležitější je ta první, která zobrazuje grafy a hodnoty:
- výkony nabíjení (příkon kW, V x A na baterce)
- SOC (%)
- GIDs (%)
- teplota baterky (st.C)
Většina dnešních rychlonabíječek nezobrazuje výkony ani proudy při nabíjení (typicky dnes velice rozšířená ABB Tera 53), ale pouze spotřebované kWh, což je z hlediska pokročilého uživatele EV zatraceně málo. Naopak Spy umožňuje při sledování výkonu nabíjení reagovat aktuálně tak, aby byl proces nabíjení co nejefektivnější a nejkratší. Např. má smysl předtopit si auto, když nabíjení jede na začátku na maximu cca 119-120A/46-47kW. Naopak nemá smysl topit, když nabíjecí výkon poklesl na nějakých 5-6kW, kdy potřebujete naládovat do auta ještě trochu energie pro dojetí do dalšího cíle. Topení za takové situace by jen zbytečně prodlužovalo čas a v některých případech i cenu nabíjení. Dále je pak neefektivní a zbytečné setrvávat na rychlonabíječce při výkonu nižším, než dovolí palubní nabíječka, když na další cestě máte pomalou AC nabíječku, ke které spolehlivě dojedete. Dál tyto grafy dají odpověď na otázku, proč je u Leafa nabíjení v zimě delší než v létě apod.

3.obrazovka
Zobrazuje údaje, které jsou i na jiných obrazovkách (Ah, SOC, GIDs, zbývající kWh, nabité/spotřebované kWh, teploty, km do cíle), takže tu moc nepoužívám, klidně by ji autor mohl vypustit.

4.obrazovka
- výkony nabíjení (V x A = kW)
- SOC (%)
- GIDs (%), GID (jednotky)
- výkon motoru,resp.příkon při nabíjení/rekuperaci
- Aux - spotřeba palub.systémů (světla, vyhřívání zad.okna apod.)
- Hetr - spotřeba topení
- A/C - spotřeba klimatizace
- Remain - zbývající kWh v baterce
- spotřeba, resp. nabité kWh
- teplota baterky (st.C) - nejvyšší, nejnižší, průměrná
- venkovní teplota (st.C)
- zbývající km (při nastavené prům.spotřebě)
- napětí (V) na baterii 12V
Tato obrazovka má největší přínos v tom, že ukazuje přehledně údaje SOC, GIDs a Remain. Zatím jsem se vyhnul popisu údaje GID/GIDs. Ani autor Spy to v manuálu nepopisuje zcela jasně. Moje zkušenosti: když se nabije auto na 100% (údaj na displeji), tak Spy zobrazuje určitý počet jednotek GID. U nové baterky je to kolem 280, u starší je to méně a odpovídá to % SOH. Toto je zřejmě klíčové, z těchto jednotek GID zřejmě Spy počítá další údaje. Podstatné je to, že když se v nastavení Spy zadá v parametru max.GIDs hodnota jednotek GID při nabití na 100%, tak údaj GIDs (%) na displeji Spy odpovídá s nějakou tolerancí % na displeji auta. Z toho plyne několik věcí. První, ta nejpodstatnější, spočívá v tom, že když na displeji auta při méně než 6% zmizí zobrazování %, tak Spy při další jízdě ukazuje % dál s přesností na desetiny %. Díky tomu jsem přišel na to, že želva přijde při cca 1,8% (Remain 0,4kWh) a auto vypne při cca 1,4% (Remain 0,3kWh). Uvedená % jsou využitelná % čili údaj % GIDs, nikoli % celkové kapacity SOC. SOC při vypnutí auta ukazuje cca 9-10% - auto si schová část energie v baterce a nedovolí vybít články až na článkové napětí kvůli jejich ochraně. Další výhodou je to, že pokud nemáte verzi Acenta a vyšší s přenosem údajů přes server Nissanu do telefonu, ale verzi Visia jako já, kde tato možnost není, tak při nabíjení a zamčeném, tedy vypnutém autě se dají na Spy i mimo auto v dosahu přenosu (BT nebo wifi) do telefonu zobrazovat aktuální údaje. Já jsem zvolil verzi OBD adaptéru-vysílače ve variantě wifi, zejména kvůli tomu, aby mě případný BT přenos dat z OBD do telefonu při jízdě neblokoval možnost použití BT handsfre pro hovory. Další výhodou tohoto řešení je, že díky wifi přenosu můžu sledovat průběh nabíjení z balkonu či obýváku našeho bytu v 3.patře paneláku. V nastavení aplikace je i možnost posílat data na nějaké úložiště a odtud to tahat do telefonu, ale k tomu jsem se zatím nedonutil.
Co se týká spotřeby topení a klimatizace, sledování těchto údajů během jízdy umožňuje efektivně topit i klimatizovat bez zbytečně vysoké spotřeby.

5.obrazovka (servisní menu, nutno aktivovat v nastavení):
- nastavení zamykání/odemykání dveří
- nastavení světel, vnitřního osvětlení
- nastavení VSP
- čtení DTC kódů

Co napsat na závěr?
Možná se to všechno někomu bude zdát jako hračička, ale já musím říct, že mě to už několikrát zachránilo před nedojetím, resp. umožnilo pustit se na trasy, kde bych si to bez Spy vůbec nedovolil. Jako občasný adrenalin není špatná věc, ale zase na druhé straně nehodlám skončit kvůli nervům v blázinci. :-)

A úplně nakonec - majitelé vyšších verzí Leafa a dalších značek, zejména Tesel klidně můžou říct "to všechno nebo skoro všechno přece v autě máme"... a mají pravdu. Bohužel u verze Visia, která se tu jako jediná prodávala před 4 lety, však zatím jinou možnost nemám.
