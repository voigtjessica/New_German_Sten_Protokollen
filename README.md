# New_German_Sten_Protokollen
Review of fetching German Stenographic Protocols using the Bundestag API
<br><br>
File: 0_retrieve_text <br>
Greate the general_df that will receive all the documents . This df has more than 25 MB so I could not upload it in the repository
<br><br>
File: 001_new_try_slicing_filtered_texts: <br>
1. Look for sections that have any of the search terms and save them in the folder ```filtered_sections```:

```
# Define the search terms and forbidden terms

search_terms_holz = [r'\bholz\w*', r'\bforst\w*', r'\bwald\w*', r'\bbioökonomie', r'\bbioenergie', r'\bmöbel\w*']

forbidden_terms = ['Holzner', 'Holzleitner', 'Waldneukirchen', 'Holzmann', 'Waldegg', 'Waldheims', 'Waldorf', 'Waldvier', 'Waldei',
                   'Holzkreuze', 'Holzweg', 'Wald4tler', 'Walddorf', 
                  'Waldkirchen', 'Waldburg', 'Waldorfschule', 'Waldspaziergang', 'Holzfuß', 'Waldzell', 'Holzleit',
                  'Waldbe', 'Waldneukirchen', 'Holzgau', 'waldorfmathematisch', 'Waldwürfe', 'Waldviertelbahn', 'Waldheim', 'Walding', 'Waldenstein', 
                  'Waldviertlerin', 'Holzlärm', 'Holzchild', 'Waldviertelautobahn', 'Holzinger', 'Waldviertler', 'Waldbrand', 'Waldbrände', 'Land- und forstwirtschaftliche Landeslehrpersonen-Dienstrechtsgesetz',
                  'Land- und forstwirtschaftliche Landesvertrags­lehr­personengesetz']
```

2. I manually marked where did every Tagesordnungpunkt (TOP) started and finished into the files, and saved a copy of each section at ```filtered_sections_marked```
3. I divided the section into TOP and searched our search terms in each of the TOPs. I saved the TOPs seperately at the folder ```filtered_tops```
4. Then I identified in the files the beginning of the president speech and the beginning of a depulty speech, and I automatically divided these speeches
5. I further sliced the TOPs into Redes
6. I searched which Rede has our search terms
7. I gathered the filtered speeches with th plenary information and saved the speeches in ```filtered_reden``` and the speeches with the information as ```reden_df_final.csv```
8.  
