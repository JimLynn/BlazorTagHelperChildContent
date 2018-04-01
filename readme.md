This project shows a possible bug in the Blazor framework.

It's trying to set an object as a member of a tag helper.
A simple button calling a method works fine, but when the
button is placed within another custom tag, as part of its
child content, that same method silently fails.

### Steps to Reproduce
1. Type in a name and description in the fields
2. Click the blue button (which lives directly in the index page) to create an instance of a Thing and set that as the Thing attribute on the Outer component. This should pass through into the nested Inner object.
3. You should see the name and description displayed twice under the buttons
4. Change the name and description and repeat, to see that the name and description change
5. Change the name again and click the green button which is nested inside another custom component as child content
6. **bug** The displayed names do not change, despite this button calling the same code as the blue button
