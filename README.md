```mermaid

%%{init: {
  "theme": "default",
  "themeCSS": [
    ".er.relationshipLabel { fill: black; }", 
    ".er.relationshipLabelBox { fill: white; }", 
    ".er.entityBox { fill: lightgray; }",
    "[id^=entity-tSpecialStatus] .er.entityBox { fill: #F9F871;} ",
    "[id^=entity-tCase] .er.entityBox { fill: #FF9671;} ",
    "[id^=entity-tPerson] .er.entityBox { fill: #FFD15F;} ",
    "[id^=entity-tCharge] .er.entityBox { fill: #C7FCEC;} ",
    "[id^=entity-tParty] .er.entityBox { fill: #00C9A7;} ",
    "[id^=entity-tSubCase] .er.entityBox { fill: #4ABAFF;} ",
    "[id^=entity-tPlea] .er.entityBox { fill: #f8f1e1;} ",
    "[id^=entity-tWarrant] .er.entityBox { fill: #C7FCEC;} ",
    "[id^=entity-tSentence] .er.entityBox { fill: #f8f1e1;} "
    ]
    
}}%%
erDiagram
    tCase ||--|| tSubCase: "case_id"
    tCase ||--|| tCaseAssignment: "case_id"
    tCaseAssignment ||--|| tPerson: "person_id"
    tSpecialStatus ||--|| tCase: "case_id"
    tPerson ||--|| tParty: "person_id"
    tCase ||--|| tParty: "case_id"
    tSubCase ||--|| tParty: "subcase_id"
    tWarrant ||--|| tParty: "associatedparty_id"
    tCharge ||--|| tParty: "associatedparty_id"
    tPlea ||--|| tCharge: "associatedcharge_id"
    tSentence ||--|| tCharge: "associatedcharge_id"
    tCase { 
        string case_id ""
        string sourcecasenumber ""
        string casename ""
        integer casenumber ""
        string casesubtype ""
        string casetype ""
        date dispositiondate ""
        string dispositiontype ""
        string location ""
        date originalfileddate ""
        integer referencenumber ""
        string status ""
        date statusdate ""
        string cf_convertcase ""
        date cf_nexteventdate ""
        string casesubtype_label ""
        string casetype_label ""
        string dispositiontype_label ""
        string location_label ""
        string status_label ""
    }
    tSubCase { 
        string subcase_id ""
        string case_id ""
        string status ""
        date statusdate ""
        string subcasetype ""
        string status_label ""
        string subcasetype_label ""
    }
    tCaseAssignment	{ 
        string caseassignment_id ""
        string case_id ""
        string person_id ""
        string assignmentrole ""
        date dateassigned ""
        string dateremoved ""
        string status ""
        string assignmentrole_label ""
        string status_label ""
    }
    tSpecialStatus { 
        string specialstatus_id ""
        string case_id ""
        date enddate ""
        date startdate ""
        string status ""
        string cf_division ""
        string status_label ""
        string cf_division_label ""
    }
    tPerson	{ 
        string person_id ""
        string personidentifier_id ""
        string firstname ""
        string lastname ""
        string middlename ""
        string persontype ""
        string cf_noirnumberavailable ""
        string persontype_label ""
    }
    tParty { 
        integer party_id ""
        string case_id ""
        string person_id ""
        string subcase_id ""
        string partysubtype ""
        string partytype ""
        string status ""
        date statusdate ""
        string nonmonapplication ""
        string partytype_label ""
        string status_label ""
        string nonmonapplication_label ""
    }
    tWarrant { 
        integer warrant_id ""
        string associatedparty_id ""
        string status ""
        integer trackingnumber ""
        string warranttype ""
        string warranttype_label ""
    }
    tCharge { 
        string charge_id ""
        string associatedparty_id ""
        string statute_id ""
        date chargedate ""
        string chargenumber ""
        string chargetype ""
        date dispositiondate ""
        string dispositiontype ""
        string eligible ""
        string status ""
        integer ticketnumber ""
        string chargetype_label ""
        string dispositiontype_label ""
        string eligible_label ""
        string status_label ""
    }
    tPlea {
        string plea_id ""
        string associatedcharge_id ""
        date pleadate ""
        string pleatype ""
        string status ""
        date statusdate ""
        string pleatype_label ""
        string status_label ""
    }
    tSentence { 
        string sentence_id ""
        string associatedcharge_id ""
        string length ""
        string lengthunit ""
        date sentencedate ""
        string sentencetype ""
        string length2 ""
        string lengthunit2 ""
        string lengthunit_label ""
        string sentencetype_label ""
        string lengthunit2_label ""
    }
```
