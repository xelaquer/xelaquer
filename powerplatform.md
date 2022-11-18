<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h2>Power Apps</h2>
    <p>
    Shadow Button aus Teams
    Dataverse create Apps copy button and parse in template  
    
    With( { de: Or( varLang = "de", varLang = "de-DE" ), en: Or( varLang =
      "en", varLang = "en-US" ) }, <br>
      <br>
      If( en, "Hello " &
      Office365Users.MyProfileV2().givenName, de, "Hallo " &
      Office365Users.MyProfileV2().givenName, "Hello " &
      Office365Users.MyProfileV2().givenName ) ) <br>
      <br>
      !Toggle Menue mit Transparent Rechteck Formeln : Rechteck OnSelect = Updatecontext:false und Rechteck
        Visible Updatecontext(Bezeichnung) 
        Choices([@'Eingabe AfS'].Anlagen)
        UpdateIf(laufendenr;ID=1;{Referenznummer:Concatenate("ME";Text(Right(Referenznummer;6)+1))});;<br>
        <br>
      Set(Bestellnummer; First(Filter(laufendenr;ID=1)).Referenznummer);;<br>
      <br>
      SortByColumns(Filter(Bedarfsmeldung;(txt_suche_3.Text in
      Status.Value&Belegnummer&Erstellt&Bezeichnung));"ID";Descending)
      If(toggle_derivat.Value=true; true; false) If(toggle_derivat.Value=false;
      true; false) Collect(colAnlagen; {Id:First(Self.Attachments).Name;
      DisplayName:"zuPos.10."&First(Self.Attachments).Name;
      Value:First(Self.Attachments).Value});; <br>
      <br>
      Derivat true :
      check_derivat_ansicht.Value=true And(Sachbearbeiter =
      varUser.mail;Status.Value="abgelehnt AL"));<br>
      <br>
      If(Len(DataCardValue14.Text)=0;false;true)
      <h3>Search for multiple Rows and Columns</h3>
      SortByColumns( Filter('Bearbeiten AfS'; And( Antragsteller = varUser.mail; Or( Status.Value =
      "genehmigt RL"; Status.Value = "Freigabe PM"; Status.Value = "Freigabe
      AL"; Status.Value = "Freigabe EK" ) ) ); "Modified"; Descending )<br>
      <br>
      If(Len(DataCardValue8.Text) = 0; DisplayMode.Disabled; 
      If(afs_b_eingabe_ansicht.Mode = 2; DisplayMode.Edit; DisplayMode.Disabled ) )<br>
      <br>
      <h3>Search for one specific Row in Column</h3>
      Or( LookUp( Produktgruppen, 'PM Sachbearbeiter' = varUser.mail, true ),
      LookUp( Produktgruppen, 'PM Vertreter' = varUser.mail, true ), LookUp(
      Produktgruppen, 'EK HW Sachbearbeiter' = varUser.mail, true ), LookUp(
      Produktgruppen, 'EK HW Vertreter' = varUser.mail, true ))<br>
      <br>
      <h3>Weekday</h3>
      If(Weekday(Now())=6, "4", Weekday(Now())=5, "5","2") <br>
      <br>
      <h3>Deep Linking</h3> <br>
      Param("screenname") = "edit" Look JSON:<br>
      <br>
    </p>

    <h2>Expressions</h2>
    <p>
      Workflow Definition Language add(79794,
      outputs('Bestellung_generieren')?['body/ID'])
      concat('AFS',formatDateTime(utcNow(),'yy'),formatNumber(add(-77,
      outputs('Element_abrufen')?['body/ID']),'00000'))
      concat(outputs('AFS_Freigabe_PM_abrufen')?['body/field_19'],'-HW')
      convertFromUtc(utcNow(), 'W. Europe Standard Time', 'dd.MM.yyyy HH:mm:ss')
      formatDateTime(triggerBody()?['Created'],'dd.MM.yyyy hh:mm:ss')
      formatDateTime(utcNow(),'dd.MM.yyyy hh:mm:ss')
      formatDateTime(outputs('Element_aktualisieren')?['body/Created'],
      'dd.MM.yyyy hh:mm:ss')
      formatNumber(outputs('Element_aktualisieren')?['body/Menge'], '#,##',
      'de')
      if(equals(outputs('AFS_finale_Freigabe_PM_RL_abrufen')?['body/Objektdatenblatt'],
      true), 'Ja', 'Nein') dataUri(outputs('Dateiinhalt_abrufen')?['body'])
      <h2>Tools</h2>
      <p>
        vscode<br>
        Swagger Editor <br>
        W3schools <br> 
        Pixabay <br>
        Googel ColorPicker <br>
        Google Fonts/Icons <br>
        Grabber <br>
      </p>

    </p>
    <h2>Sonstiges</h2>
    <p>
      Name: Test-Workflow <br />
      Kennwort:TWF!2022-02-02 <br />
      E-Mail: Test-Workflow@Naue.com
    </p>
  </body>
</html>
