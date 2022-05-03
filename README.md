Sukurkite paprastą duomenų tvarkymo programą (Geriausia python, duomenims galima naudoti panda frameworką, tačiau nėra būtina). Progama turėtų būti vykdoma konsolėje (CLI).
Žingsniai, kuriuos turėtų atlikti programą:
1) Duomenų gavimas
	- Apjungti pirminius duomenų rinkinius(task_data_1.csv, task_data_2.csv) į bendrą duomenų rinkinį, tačiau duomenų rinkinių skaičius iš anksto nėra žinomas, programa  turi gebėti be papildomų pakeitimų apdoroti N duomenų rinkinius.
	- Prie gauto bendro duomenų rinkinio prijungti POLICY_DATA naudojant policy_id stulpelį
2) Duomenų tvarkymas. Reikalavimai:
	- "car_brand" tuščius laukus pakeisti į daugiausiai pasikartojantį įrašą (modą)
	- "car_age" sukurti naują stupėlį, paskaičiuojantį automobilio amžių. Naudoti "car_registration_year" stulpelį ir dabartinę datą. Galiausiai jį sugruopuoti į 4 intervalus (pvz. [0,10), [10,15) ir t.t.)
	- "car_eng_pow" tuščius laukus pakeisti į "-1" reikšmę, vėliau visą stulpėlį sugrupuoti į "0-100", "100-250", "250+" grupes
	- "customer_age" tuščius laukus pakeisti į "-1" reikšmę, vėliau visą stulpėlį sugrupuoti į intervalus po 10, prasidedančius nuo 20 iki 100. Laukai su "-1" reikšmė turėtų būti sugrupuoti į mažiausią intervalą
	- "postal_code" tuščius laukus pakeisti į dažniausiai pasikartojantį įrašą (modą). Visi stulpelio įrašai negali turėti "whitespace" bei "-" ženklų
	- "marital_status" pergrupuoti sekančiu budu: 1 - "Single", 2 - "Married". Tušti laukai turėtų būti sugrupouti į "Single" grupę
	- "claim_amount" tuščius laukus pakeisti į nulį
	- Pakeisti visų datos stulpelių tipą į "datetime"
3) Rezultato apskaičiavimas
	- Sukurti naują stulpelį "exposure" naudojantis "policy_start", "policy_end" ir "claim_amount" stulpėliais. "policy_start" ir "policy_end" dienų skirtumą reikia padalinti iš 365 ir gautą reiškmę išsaugoti "exposure" stulpelyje. Jeigu gauta reikšmė yra didesne už vienetą, ją pakeisti "1". Jeigu įrašo "claim_amount" reikšmė yra "0", tai "exposure" lygus nuliui.

Kiekvieną iš šių žingsnių turi būti galimybė paleisti nepriklausomai, paleidžiant programą su atitinkamais argumentais, jie identifikuotų kurį programos žingsnį reikia vykdyti.


(Nebūtina dalis)Bonus taškai už:
-Bent keli Unit testai (tam gali būti naudojamas bet koks framework'as).
-Galimybė importuoti ir saugoti .parquet formato duomenis. Pavyzdinis .parquet failas turėtų būti pridėtas prie kodo.
-Galimybė pakeisti duomenų tvarkymo taisyklės tiesiogiai nekeičiant kodo.


