<template>
  <div id="app">
    <h1 id="naslov">Breaking Bad</h1>
    <h2 id="podnaslov">O seriji</h2>
    <p id="text">Na putu prema dolje (engl. Breaking Bad), američka je kriminalistička dramska televizijska serija čiji je autor i producent 
      Vince Gilligan. Serija se originalno emitirala na televizijskoj mreži AMC, a trajala je sveukupno pet sezona od 20. siječnja 2008. 
      do 29. rujna 2013. godine. Radnja serije vrti se oko Waltera Whitea (Bryan Cranston), profesora kemije u srednjoj školi kojem je 
      dijagnosticiran neoperabilni rak pluća. Zajedno sa svojim bivšim učenikom Jessejem Pinkmanom (Aaron Paul), White se okreće svijetu 
      kriminala producirajući i prodavajući kristalizirani metamfetamin, a sve kako bi osigurao financijsku budućnost svoje obitelji prije 
      vlastite smrti. Originalni naslov serije Breaking Bad proizašao je iz južnjačkog govornog izraza koji znači raise hell 
      (u slobodnom prijevodu "uzburkati pakao"). Radnja serije Na putu prema dolje smještena je u Albuquerque (država Novi Meksiko).
      <br><br>
      Walterovu obitelj čine njegova supruga Skyler (Anna Gunn) te dvoje djece - Walter Jr. (RJ Mitte) i Holly (Elanor Anne Wenrich). 
      Ostali likovi serije uključuju Skylerinu sestru Marie Schrader (Betsy Brandt) i njezinog muža Hanka (Dean Norris), agenta DEA-e. 
      U jednom trenutku serije Walter unajmljuje odvjetnika Saula Goodmana (Bob Odenkirk) koji ga spaja s privatnim istražiteljem Mikeom 
      Ehrmantrautom (Jonathan Banks) te, u konačnici, s njegovim poslodavcem, a ujedno i narkokraljem Gusom Fringom (Giancarlo Esposito). 
      U posljednjoj sezoni kao jedni od glavnih likova pojavljuju se Todd Alquist (Jesse Plemons) i Lydia Rodarte-Quayle (Laura Fraser).
      <br><br>
      Na putu prema dolje vrlo učestalo se smatra jednom od najboljih televizijskih serija svih vremena. 
      Do trenutka kada je emitirana posljednja epizoda, serija se nalazila među najgledanijim programima američke kablovske televizije. 
      Osvojila je mnogobrojne nagrade uključujući šesnaest prestižnih televizijskih nagrada Emmy, osam nagrada Satelit, dva Zlatna Globusa, 
      dvije nagrade "Peabody", dvije nagrade Udruženja filmskih kritičara te četiri nagrade Udruženja televizijskih kritičara. 
      Za nastup u seriji Cranston je četiri puta osvojio televizijsku nagradu Emmy u kategoriji najboljeg glavnog glumca; 
      Aaron Paul je osvojio tri Emmyja u kategoriji najboljeg sporednog glumca dok je Anna Gunn osvojila dva Emmyja u kategoriji najbolje 
      sporedne glumice. Godine 2013. serija Na putu prema dolje ušla je u Guinnessovu knjigu rekorda kao kritičarski najbolje ocijenjena 
      serija svih vremena.
    </p>
    <div v-b-visible="dohvatiPod"></div>
    <h2 id="podnaslov">Glumci</h2><br>
    <div id="kartica">
      <b-row>
        <b-col class="col-4" v-for="g in glumci" v-bind:key="'g' + g.id">
          <b-card id="card"
            :title="g.portrayed"

            :img-src="g.img"
            img-alt="Image"
            img-top
            
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
              <p>Glumi: {{g.name}}</p>
              <p>Nadimak: {{g.nickname}}</p>
              <p>Uloga u seriji: {{g.occupation}}</p>
              <p>Datum rođenja: {{g.birthday}}</p>


            </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "Pocetna",
  data: function () {
    return {
      glumci: []
    };
  },
  methods: {
    dohvatiPod: function () {
      this.axios
        .get("https://breakingbadapi.com/api/characters")

        .then((response) => {
          console.log(response);
          this.glumci = response.data;
        });
    }
    
  },
};
</script>
<style >
  #text{
    text-align:justify;
    margin-left:20px;
    margin-right:20px;
    
  }
  #naslov{
    text-align:center;
    font-size:70px;
  
    
  }
  #podnaslov{
    margin-left:20px;
  }
  #kartica{
    margin-left:40px;
    
  }
  
</style>
