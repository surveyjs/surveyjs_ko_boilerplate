# SurveyJS KnockoutJS quickstart boilerplate

## How to run this sample application
 - git clone https://github.com/surveyjs/surveyjs_ko_boilerplate.git
 - cd surveyjs_ko_boilerplate
 - npm i
 - npm start
 - open http://localhost:8080/ in your web browser


## Add survey component on your page

```HTML
<survey params="survey: surveyModel"></survey>
```

```JavaScript
 //Define Survey JSON
 //Here is the simplest Survey with one text question
 json = {
  elements: [
   { type: "text", name: "customerName", title: "What is your name?", isRequired: true}
  ]
 };

  //Create the model and pass it into knokout Survey application model
  //The most model properties are reactive, on their change the component will change UI when needed.
  var model = new Survey.Model(json);
  // You can set properties of the survey model model
  // model.mode="display"

  //You cam use survey model as a part of your knockout apoplication model
  var outerModel = {
      myAppName: "My Application",
      surveyModel: model
  }

  // Choose survey appearance - apply theme
  Survey.StylesManager.applyTheme("orange");
  
  // Apply knockout bindings to a whole page
  ko.applyBindings(outerModel);
```
