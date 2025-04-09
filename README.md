# AdvancedRegressionTechniques

## პროექტი
ჩვენი მიზანი იყო ამოგვეხსნა ამოცანა kaggle-იდან House Prices - Advanced Regression AdvancedRegressionTechniques, სადაც მოცემული გვაქვს სახლების უამრავი მახასიათებელი, მაგალითად სარდაფის, პირველი და მეორე დართულის ფართობი, ღობის და აუზის ხარისხი, სახურავის მასალა და სხვები, ჯამში 79 და ჩვენი მიზანია გავწვრთნათ მოდელი, რომელიც შეძლებს სახლების ფასის გამოცნობას.

## რეპოზიტორიის სტრუქტურა
- model_experiment.ipynb - ძირითადი სამუშაო ფაილი, სადაც ხდება შემოსული ინფორმაციის cleaning, feature engineering/selection და მოდელის გაწვრთნა, რომლებიც ილოგება mlflow-ზე შემდგომი გამოყენებისთვის.
- model_inference.ipynb - მოდელი, რომელმაც საუკეთესო შედეგი მოგვცა, იტვირთება mlflow-დან და ეშვება სატესტო მონაცემებზე.

## Feature Engineering
კატეგორიული ცვლადების რიცვებად გადაყვანა ხდება OneHotEncoding ის საშუალებით, თუ კატეგორიულ ცვლაბეს მნიშვნელობა არ აქვთ, ვავსებთ 'None' სტრინგით, ხოლო რიცხვითებს 0-ით.

## Feature Selection
დავამატე დამატევბითი feature-ები, რომლებიც გვეუბნება მთლიან ფართობს, აქვს თუ არა ბუხარი, აუზი, გარაჟი და სარდაფი, რადგან ამ მონაცემებს უკეთესი კორელაცია აქვთ საბოლოო ფასთან.

## Training
თავდაპირველად გამოვიყენე Linear Regression, რამაც მომცა მაღალი ცდომილება, ~65 000, რაც აშკარად undefit ითაა გამოწვეული, ამიტომ დავამატე ახალი feature ები და მოდელი შევცვალე Ridge ით, რამაც ცდომილება ბევრად შეამცირა (~30 000). ბოლოს, cleaning გავიტანე pipeline ში რადგან ამგვარად, სატესტო run ზე მოდელის გამოყენება ბევრად მარტივდება.

## MLflow Tracking
> https://dagshub.com/gioeba/AdvancedRegressionTechniques.mlflow
თითოეული გაშვებისთვის დავლოგე კონკურსისთვის ცდომილების საზომი კრიტერიუმი, RMSE. საუკეთესო მოდელმა მომცა ~30,000 ის ცდომილება.


