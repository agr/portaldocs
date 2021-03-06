<a name="accessibility-planning"></a>
## Accessibility Planning

As we continue to work through our accessibility backlog we would like to streamline the process as best we can to be as efficient as possible. Below is a template to help guide you through what tags to use as bugs are filed. Most (95%) of bugs will fall into one of the 8 issues below. All bugs that you feel are framework issues should be assigned to Paymon Parsadmehr. If you feel a bug falls into more than one category, please add all corresponding tags to the bug. If you feel the bug does not fit into any of the buckets please reach out to me (paparsad) and we can take a look together to see where it fits. As we resolve each bucket we will send out updates for folks to be aware of the progress as well as be ready for regress testing from vendor teams. Please reach out to me if there are any other questions or concerns. 
 
 
Below are the tagging rules as well as examples of each bug class. 
<a name="accessibility-planning-alternate-text-tag-alttext"></a>
### Alternate Text- (tag AltText)
  Screen reader reads the text content, but the output is not helpful, or the output needs to be more descriptive, or no output is read except the control type.
1.   Example: Screen reader cursor is on a part and all the part content is read instead of expected text.
1.   Example: Screen reader cursor is on an option picker control and all the options are read instead of a label.
1.   Bug example: [RDBug 8105335](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8105335):Azure API Management Service: More Services: Name Property is Empty for "Search the Market Place" edit box
 
**Alternate Text** will require downstream code changes. This is our top priority at the  moment. Will send updates as we release SDK’s with updated controls. 

<a name="accessibility-planning-aria-attribute-tag-aria-attr"></a>
### Aria-attribute- (tag Aria-attr)
  Functionality not exposed to screen readers. Examples: expandable, multi-selectable, item position and index, etc.
1.  Bug example: [RDBug 8259873](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8259873): Accessibility: MAS40B: Inspect: "Name" property is empty for 'Create' group.[Scenario: Creating NameSpace]
 

<a name="accessibility-planning-contrast-ratio-tag-contrastratio"></a>
### Contrast-Ratio – (tag Contrastratio)
Contrast ratio of text color against background is insufficient (high contrast is a different issue).
1.   Example: Text does not have a contrast ratio of at least 7:1 on button in the “Azure” theme.
1.   Bug example: [RDBug 8091694](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8091694):[Accessibility] Luminosity contrast ratio is less than 4.5:1 for "Support" link in feedback pane under "Blue Alt" theme
 
<a name="accessibility-planning-high-contrast-tag-highcontrast"></a>
### High Contrast- (tag Highcontrast)
All issues related to High Contrast mode.
1.   Example: Focus not visible while using High Contrast Black-on-White mode in Edge on buttons.
1.  Bug example: [RDBug 8133287](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8133287):Ibiza Portal: Accessibility: High Contrast - Black: Data Lake: All Resources: Previous Page button is not visible in High Contrast - Black Theme
  
<a name="accessibility-planning-focus-management-tag-focus-management"></a>
### Focus-management- (tag Focus-management)
Focus set at an unexpected place, or focus is lost, or focus is trapped.
1.   Example: Focus lost when switching value in dropdown via keyboard.
1.   Example: Cannot focus away from button once it captures focus.
1.  Bug example: [RDBug 8679020](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8679020):[Keyboard Navigation - KeyVault -Select Principle ] Focus order is not logical on the "Select Principle" blade.
 
<a name="accessibility-planning-keyboard-accessibility-tag-keyboardaccess"></a>
### Keyboard Accessibility – (tag KeyboardAccess)
Activation and interaction via keyboard not working as expected or is inconsistent, or the item cannot be accessed via keyboard.
1.   Example: Cannot tab to button.
1.   Example: Cannot activate button with spacebar key.
1.  Bug example: [RDBug 8220516](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8220516):[Ibiza Portal]: Accessibility: MAS36: KB: Unable to access the Add to Favorites button (star button) for (Service Bus, Event Hubs, Relays) when navigated from "More Services -> Search Filter -> Service Bus/Event Hubs/Relays".
 
<a name="accessibility-planning-grid-tag-grid"></a>
### Grid- (tag Grid)
All issues related to Grid, regardless of the previous issues mentioned.
1.  Example: Grid does not expose the column header on the cell (would be Aria-attr, yet triages as Grid).
1.  Bug example: [RDBug 8882413](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8882413):Ibiza Portal:[B2A][E2A][E2E][V2A]Accessibility: Inspect :MAS40B: Name property is Inappropriate for column header items in 'Jobs' page of Azure portal.
 
<a name="accessibility-planning-listview-tag-listview"></a>
### ListView- (tag ListView)
All issues related to ListView, regardless of the previous issues mentioned.
1. Example: ListView does not read any content when focus is set on an element (would be AltText, yet triage as ListView).
1. Bug example: [RDBug 8133284](http://vstfrd:8080/Azure/RD/_workitems#_a=edit&id=8133284):ibiza portal: Usability: Narrator: Intune Data Lake: New: Narrator announces Contains 0 items for a list of 3 or more items
 
 
 
Additional guidance
1.   Some of the bugs you got may contain multiple issues described in them (Ex: scenario 1, scenario 2). Please separate those issues in separate bugs. Bugs with multiple issues cannot be resolved reliably.
1.   Ensure the attachments(img, png) files contain screenshots with highlighted problem areas. Videos alone have not been helpful.
1.   Screen reader issues (AltText and Aria-attr labels) should be reported from testing with Edge using Narrator, or Firefox using NVDA. Other combinations will be deferred.
1.   Screen reader fixes will be done for Edge using Narrator on Windows 10 Creators Update, and Firefox with NVDA. Regression testing should take those consideration into account, we will inform the vendors team of this.
1.   Iframes are not a part of the scope and do not have any dependencies on the framework. Extensions are advised to test these scenarios on their own and are responsible for fixes.
1.   Some legacy controls will be deprecated and extensions will need to move to the updated version of the control in order to meet accessibility standards due to cost issues. 
 
**updating legacy controls will require extension code changes. We are working on a list of these controls and will share by end of the April. 

1.   Use the following [bug template](http://vstfrd:8080/Azure/RD/_workItems#_a=new&witd=RDBug&%5BSystem.AssignedTo%5D=Paymon%20Parsadmehr%20%3CNORTHAMERICA%5Cpaparsad%3E&%5BSystem.Description%5D=%3Cp%3E%3Cb%3EUpdate%26nbsp%3Bthe%20following%20fields%20and%20erase%20these%20instructions%3A%3C%2Fb%3E%3C%2Fp%3E%3Cp%3E1-%20Change%20TITLE%3C%2Fp%3E%3Cp%3E2-%20Add%20proper%20TAGS%20%28see%20email%29%3C%2Fp%3E%3Cp%3E3-%20Ensure%20FILE%20ATTACHMENTS%20include%20a%20screenshot%20circling%20the%20issue%20area%20with%20brief%20text.%20Videos%20aren%27t%20sufficient.%20Please%20don%27t%20use%20zip%20files.%3C%2Fp%3E%3Cp%3E4-%20Update%20DESCRIPTION%20with%20repro%20to%20problem%20area%20and%20expected%20behavior.%20No%20MAS%20description%2C%20no%20sample.%20Just%20repro%20and%20expectation.%3C%2Fp%3E&%5BMicrosoft.Rd.HowFound%5D=Acceptance&%5BMicrosoft.Azure.IssueType%5D=Code%20Defect&%5BSystem.AreaPath%5D=RD%5CAzure%20App%20Plat%5CAzurePortal%5CFx&%5BSystem.IterationPath%5D=RD%5CAzure%20App%20Plat%5CIbiza%5CNext) to file bugs 
