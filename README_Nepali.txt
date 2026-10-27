विद्यालय तलब व्यवस्थापन प्रणाली — अनलाइन सेटअप

महत्त्वपूर्ण: यो फाइल बनाइएको/जाँच गरिएको हो, तर Firebase project मा deployment र वास्तविक login परीक्षण नगरी अनलाइन चलिरहेको छ भन्न मिल्दैन।

१) पहिला पुरानो प्रणालीमा Backup/Export गरेर सुरक्षित राख्नुहोस्। तलब हिसाबका मूल सूत्रहरू नबदल्ने उद्देश्यले मूल HTML बाट Cloud/Auth मात्र जोडिएको छ, तर प्रयोगमा ल्याउनु अघि परीक्षण गर्नुहोस्।

२) Firebase Console खोल्नुहोस्: https://console.firebase.google.com/
   Project: salary-management-syatem
   Authentication > Sign-in method > Email/Password Enable भएको हुनुपर्छ।
   Authentication > Users > Add user मा एकपटक साझा खाता बनाउनुहोस्:
   Email: admin@salary-management-syatem.firebaseapp.com
   Password: तपाईंले रोजेको बलियो पासवर्ड (कम्तीमा ६ अक्षर; admin123 भन्दा बलियो राख्नुहोस्)।

३) Firestore Database > Rules मा firestore.rules फाइलको नियम राखेर Publish गर्नुहोस्। नियमले लगइन भएको एउटै खातालाई आफ्नै cloud document पढ्न/लेख्न दिन्छ।

४) GitHub मा नयाँ repository बनाउनुहोस्। यस प्याकेटबाट index.html र firestore.rules फाइल GitHub मा upload गर्नुहोस्। GitHub Pages ले index.html लाई website को रूपमा publish गर्न सक्छ; Firebase Console मा Authentication > Settings > Authorized domains मा GitHub Pages domain (username.github.io) थप्नुहोस्।

५) वेबसाइट पहिलोपटक खोल्दा पहिले data भएको कम्प्युटर/डिभाइसबाट लगइन गर्नुहोस्। यदि Cloud मा पहिल्यै डाटा छैन भने यही डिभाइसको स्थानीय डाटा cloud मा पहिलोपटक लेखिन्छ। खाली डिभाइसबाट पहिला लगइन नगर्नुहोस्।

६) सबै डिभाइसमा Username: admin र माथि बनाएको एउटै Password प्रयोग गर्नुहोस्। पासवर्ड परिवर्तन गर्ने सुविधा प्रणालीभित्र छ; परिवर्तन गरेपछि सबै डिभाइसमा नयाँ पासवर्ड लाग्छ।

७) अन्य डिभाइसमा खोल्दा पहिले cloud data load भएको/Cloud Sync जडान भयो भन्ने स्थिति हेर्नुहोस्। परीक्षण नभएसम्म वास्तविक तलब हिसाबमा निर्भर नगर्नुहोस्। एउटा डिभाइसबाट परिवर्तन गरेपछि Cloud मा सुरक्षित भयो भन्ने देखिएपछि मात्र बन्द गर्नुहोस्। नियमित Backup/Export गर्नुहोस्।

सुरक्षा नोट: सबैले एउटै खाताले लगइन गर्ने हुँदा सबैको समान पहुँच हुन्छ; कसले के परिवर्तन गर्‍यो भनेर छुट्याउन सकिँदैन। GitHub repository सार्वजनिक भए पनि HTML मा Firebase config देखिनु सामान्य हो, तर Firestore Rules र Auth configuration अनिवार्य छन्।
