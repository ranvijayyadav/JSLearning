
source https://cwiki.apache.org/confluence/display/solr/Suggester 

    Suggester 
    
    The SuggestComponent in Solr provides users with automatic suggestions for query terms.
    You can use this to implement a powerful auto-suggest feature in your search application.
    
    The main features of this Suggester are:
        1:>Lookup implementation pluggability
        2:>Term dictionary pluggability, giving you the flexibility to choose the dictionary implementation
        3:>Distributed support
        
        
    Configuring Suggester in solrconfig.xml
    
        1:>Adding the Suggest Search Component
           The first step is to add a search component to solrconfig.xml and tell it to use the SuggestComponent. 
           Here is some sample code that could be used.
           
           <searchComponent name="suggest" class="solr.SuggestComponent">
             <lst name="suggester">
               <str name="name">mySuggester</str>
               <str name="lookupImpl">FuzzyLookupFactory</str>
               <str name="dictionaryImpl">DocumentDictionaryFactory</str>
               <str name="field">cat</str>
               <str name="weightField">price</str>
               <str name="suggestAnalyzerFieldType">string</str>
               <str name="buildOnStartup">false</str>
             </lst>
           </searchComponent>
           
           