The litte code to generate your vote in the upcoming election in Poland.
All canidates are present, the generator takes input and tries to choose on the candiates based on the weather that will be present on 18 May 2025.
All prequestions are present in the code, but also present below:

      let wagi = kandydaci.map(k => {
        let waga = 1.0;

        if (temperatura > 24 && k.wiek < 50) waga *= 1.5;
        else if (temperatura < 15 && k.wiek > 50) waga *= 1.5;

        if (cisnienie < 1010 && k.wyksztalcenie === "średnie") waga *= 1.5;
        else if (cisnienie >= 1010 && k.wyksztalcenie === "wyższe") waga *= 1.5;

        if (opady && k.miasto === "Warszawa") waga *= 1.5;

        if (wilgotnosc > 80 && k.wiek > 50) waga *= 1.3;
        if (wiatr > 30 && k.wiek < 50) waga *= 1.3;

        if (wschod < "05:00" && k.miasto === "Warszawa") waga *= 1.2;
        if (zachod > "20:00" && k.wyksztalcenie === "wyższe") waga *= 1.2;

        return waga;
      });
