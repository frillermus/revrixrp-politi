# RevrixRP Politihåndbog

Dansk, mobilvenlig politihåndbog med login, procedurer, rettighedsoplæsning og rangoversigt. Siden følger den mørkeblå/grønne, enkle kortstil fra dine øvrige Supabase-baserede sider. Håndbogens første indhold er udarbejdet ud fra `Rankorden.html` og `Rettigheder.html`.

## Opsætning

1. Åbn det Supabase-projekt, hjemmesiden skal bruge, og kør hele `supabase-politi-setup.sql` i **SQL Editor**. Scriptet opretter håndbogs- og rangtabeller, RLS-læseadgang for indloggede brugere og indsætter grundindholdet. Det kan køres igen for at opdatere seed-indholdet.
2. Siden bruger Supabase-projektet og loginmønstret fra dine eksisterende sider (`frillermus/bennys-ambulance`): fornavn + efternavn + kode. Der skal allerede findes en Supabase Auth-konto for medarbejderen.
3. Udgiv `index.html` på GitHub Pages eller din foretrukne statiske hosting. Ingen build-trin er nødvendige.

Hvis du vil bruge et andet Supabase-projekt, skift `SUPABASE_URL` og `SUPABASE_PUBLISHABLE_KEY` øverst i `index.html` til det projekts URL og publishable key. Brug aldrig en `service_role`-nøgle i browserkode.

## Indhold og adgang

- Supabase Auth beskytter siden; indhold vises kun efter login.
- `police_handbook_sections` gemmer artikler og struktureret indhold. `police_ranks` gemmer rangnumre, distrikter og beføjelser.
- RLS giver autentificerede brugere læseadgang. Kun databaseejeren/Supabase-administratoren bør redigere data via SQL Editor.
- Søgefelterne filtrerer procedurer og rangoversigten direkte i browseren.
- Rangnavne, der ikke fremgik af det givne materiale, er bevidst tomme, så de kan udfyldes senere.
- Strikes-proceduren er markeret som generel huskeliste, fordi de konkrete regler ikke var medsendt.

## Bemærk

Rettighedsteksterne og tidsgrænserne er gengivet som rollespilsindhold fra de medsendte filer. De er ikke juridisk rådgivning og beskriver ikke virkelige myndighedsbeføjelser. Serverens aktuelle regler og instrukser har altid forrang.
