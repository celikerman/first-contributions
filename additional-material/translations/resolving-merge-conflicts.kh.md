# តើជម្លោះរួមបញ្ចូលគ្នាគឺជាអ្វី?

នៅពេលអ្នកព្យាយាមបញ្ចូលសាខាមួយទៀតទៅក្នុងសាខាដែលកំពុងធ្វើការបច្ចុប្បន្នរបស់អ្នក អ្នកកំពុងទទួលយកការផ្លាស់ប្តូរពីបរិបទផ្សេងទៀត ហើយបញ្ចូលពួកវាជាមួយឯកសារដែលកំពុងធ្វើការបច្ចុប្បន្នរបស់អ្នក។
ប្រសិនបើមនុស្សពីរនាក់បានផ្លាស់ប្តូរបន្ទាត់ដូចគ្នានៅក្នុងឯកសារតែមួយ ឬប្រសិនបើមនុស្សម្នាក់សម្រេចចិត្តលុបវា ខណៈពេលដែលអ្នកផ្សេងទៀតសម្រេចចិត្តកែប្រែវា Git មិនអាចកំណត់អត្តសញ្ញាណមួយណាជាកំណែត្រឹមត្រូវបានទេ។ បន្ទាប់មក Git នឹងសម្គាល់ឯកសារថាមានជម្លោះ ដែលអ្នកនឹងត្រូវដោះស្រាយ មុនពេលអ្នកអាចបន្តការងាររបស់អ្នក។

# តើធ្វើដូចម្តេចដើម្បីដោះស្រាយជម្លោះរួមបញ្ចូលគ្នា?

នៅពេលប្រឈមមុខនឹងការប៉ះទង្គិចគ្នា git នឹងសម្គាល់តំបន់ដែលមានបញ្ហានៅក្នុងឯកសារដោយភ្ជាប់វានៅក្នុង “<<<<<<< HEAD” និង “>>>>>>>>>> [ឈ្មោះសាខាផ្សេងទៀត។]"

ខ្លឹមសារបន្ទាប់ពីសញ្ញាសម្គាល់ទីមួយមានប្រភពចេញពីសាខាការងារបច្ចុប្បន្នរបស់អ្នក។ បន្ទាប់ពីតង្កៀបមុំ Git ប្រាប់យើងពីកន្លែងដែល (សាខាណា) ការផ្លាស់ប្តូរបានមកពី។ បន្ទាត់ដែលមាន "=======" បំបែកការផ្លាស់ប្តូរដែលផ្ទុយគ្នាទាំងពីរ។
ការងាររបស់យើងឥឡូវនេះគឺដើម្បីសម្អាតបន្ទាត់ទាំងនេះ៖ នៅពេលដែលយើងរួចរាល់ ឯកសារគួរតែមើលទៅដូចដែលយើងចង់ឱ្យវាមើលទៅ។ វាត្រូវបានណែនាំឱ្យពិគ្រោះជាមួយមិត្តរួមក្រុមដែលបានសរសេរការផ្លាស់ប្ដូរដែលផ្ទុយគ្នា ដើម្បីសម្រេចថាតើកំណែណាមួយគួរតែជាចុងក្រោយ។ វាអាចជារបស់អ្នក ឬប្រហែលជាល្បាយរវាងអ្នកទាំងពីរ។

e.g. :
```
 <<<<<<< HEAD:mergetest
 នេះជាជួរទីបីរបស់ខ្ញុំ
 =======
 នេះជាជួរទីបួនដែលខ្ញុំកំពុងបន្ថែម
 >>>>>>> 4e2b407f501b68f8588aa645acafffa0224b9b78:mergetest
```

`<<<<<<<`: ចង្អុលបង្ហាញការចាប់ផ្តើមនៃបន្ទាត់ដែលមានជម្លោះបញ្ចូលគ្នា។ សំណុំបន្ទាត់ដំបូងគឺជាបន្ទាត់ពីឯកសារដែលអ្នកកំពុងព្យាយាមបញ្ចូលការផ្លាស់ប្តូរទៅក្នុង។
`=======`: ចង្អុលបង្ហាញចំណុចបំបែកដែលប្រើសម្រាប់ការប្រៀបធៀប។ បំបែកការផ្លាស់ប្តូរដែលអ្នកប្រើប្រាស់បានប្តេជ្ញាចិត្ត (ខាងលើ) ចំពោះការផ្លាស់ប្តូរដែលមកពីការបញ្ចូលគ្នា (ខាងក្រោម) ដើម្បីមើលឃើញភាពខុសគ្នា។
`>>>>>>>`: ចង្អុលបង្ហាញចុងបញ្ចប់នៃបន្ទាត់ដែលមានជម្លោះបញ្ចូលគ្នា។

អ្នកដោះស្រាយជម្លោះដោយការកែសម្រួលឯកសារ ហើយបន្ទាប់មកបញ្ចូលផ្នែកនៃឯកសារដែល git មានបញ្ហាក្នុងការបញ្ចូលគ្នាដោយដៃ។ នេះអាចមានន័យថាបោះបង់ការផ្លាស់ប្តូររបស់អ្នក ឬរបស់អ្នកផ្សេង ឬបន្តទៅមុខជាមួយនឹងការលាយបញ្ចូលគ្នានៃទាំងពីរ។ អ្នកក៏នឹងត្រូវលុប '<<<<<<<', '=======' និង '>>>>>>> នៅក្នុងឯកសារ។

នៅពេលដែលអ្នកបានដោះស្រាយជម្លោះ ធ្វើ `git add` ។ កុំភ្លេចដំណើរការការធ្វើតេស្តព្រោះអ្នកត្រូវតែប្រាកដថាអ្នកបានដោះស្រាយជម្លោះ។

អ្នកក៏អាចទាញយកកម្មវិធីជំនួយផ្សេងៗ អាស្រ័យលើ IDE ដែលអ្នកកំពុងប្រើ សម្រាប់វិធីងាយស្រួលជាងក្នុងការដោះស្រាយជម្លោះបញ្ចូលគ្នា។


# តើធ្វើដូចម្តេចដើម្បីលុបចោលការបញ្ចូលគ្នា?
ប្រសិនបើ​អ្នក​ចង់​មិន​ធ្វើ​ការ​បញ្ចូល​គ្នា​វិញ អ្នក​អាច​ធ្វើ `git merge —abort`