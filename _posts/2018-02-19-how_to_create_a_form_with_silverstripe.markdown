---
layout: post
title:      "How to Create a Form with SilverStripe"
date:       2018-02-19 21:04:41 +0000
permalink:  how_to_create_a_form_with_silverstripe
---


Although Rails Form will always have my heart, I would like to share a little about something new I learned regarding form creation. I have been working on learning SilverStripe and this was my latest project with the platform.

SilverStripe's CMS comes with a way to create a form page right from the browser.
1. Select add new page
2. Select page type to be form
3. Choose field type
* If you choose a field type that contains sub-fields, such as dropdown or checkbox, save first, then choose edit to create options within  the field.
4. Enter title
5. Save & Publish

You can also create a form through your editor which is connected to the CMS.
1. Create a *FormPage*.php file within the mysite/code directory
2. Create a *FormPage*Controller.php file within the mysite/code directory
3. Establish form function in **controller**. Make sure to "use" necessary SilverStripe extensions.
```public function Form()
    {
        $form = Form::create(
            $controller,
            'Form',
            FieldList::create(
                TextField::create('Name','Your name'),
                TextareaField::create('Comment','Your comment')
								DateField::create('Date','Today's date')
            ),
            FieldList::create(
                FormAction::create('submitForm','Submit')
            )
        );

        return $form;
    }```
4. Optional: Add requirements to form
5. Allow form function to be used by adding this at top
```
class FormController extends PageController
{

  private static $allowed_actions = [
    'Form' <-- name of form function declared above
  ];
	
	public function submitForm($data, $form)
	...
```
6. Create submission function in **controller**. Note that function name is the same as that declared in FormAction::create above
```public function submitForm($data, $form)
    {
        $name = $data['Name'];
        $comment = $data['Comment'];
				$date = $data['Date']

        return $this->redirectBack(); <-- you can edit this to redirect to a specific url using redirect('*url*')
    }```


I am now working on what to do after the form is submitted. Stay tuned for my next post!
