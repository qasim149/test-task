# Test task

## Javascript:

1. **What is your favourite new javascript feature and why?**

   - Destructuring
   - Because we can extract data from arrays and objects in single line.

2. **Explain an interesting way in which you have used this javascript feature.**

   ```
   const employer = {
       name: 'John',
       lastName: 'Doe'
       job: {
           title: 'developer',
           salary: "$1200"
       }
   }

   ```

   ```
   const { name, lastName, age = 20, job: { title: jobTitle, salary } } = employer;
   ```

   - We can unpact the object(employer) easily
   - We can mutate
   - Nested destructuring(most favourite feature)
   - Also assing a new name to the property like title to jobTitle

3. **Is there any difference between regular function syntax and the shorter arrow function syntax? (Write the answer in your own words)**

   - Yes
   - Regular Functions
     ```
         function fn() {
             // body
         }
     ```
     - Regular functions are created by using function declaration and regular functions are callable and constructible like fn().
     - Its own bindings to the this, arguments etc.
   - Arrow Functions
     ```
         const fn = () => {
             // body
         }
     ```
     - While arrow functions are not its own bindings.
     - Arrow functions are only callable.

4. **What is the difference between ‘myFunctionCall(++foo)’ and ‘myFunctionCall(foo++)’**

   - myFunctionCall(++foo)
     - The parameter(foo++) in above function will increase by one with function call.
   - myFunctionCall(foo++)
     - The parameter(++foo) in above function will increase by one after function call.

5. **In your own words, explain what a javascript ‘class’ is and how it differs from a function.**
   - Javascript classes
   - These are actually type of javascript functions
   - We use class keyword to declare a class While functions in javascript are declared with function keyword
   - We can wrap multiple functions in a class

## CSS:

6. **In your own words, explain css specificity**

   - If there are two or more conflicting CSS rules that point to the same element, the browser follows some rules to determine which one is most specific and therefore wins out.
   - Think of specificity as a score/rank that determines which style declarations are ultimately applied to an element.
   - The universal selector (\*) has low specificity, while ID selectors are highly specific!

7. **In your own words, explain, what is ‘!important’ in css. Also how does it work? Are there any special circumstances when using it, where it’s behaviour might not be what you expect?**

   - It means, essentially, what it says; that 'this is important, ignore subsequent rules, and any usual specificity issues, apply this rule!'
   - In normal use a rule defined in an external stylesheet is overruled by a style defined in the head of the document, which, in turn, is overruled by an in-line style within the element itself (assuming equal specificity of the selectors). Defining a rule with the `!important` 'attribute' (?) discards the normal concerns as regards the 'later' rule overriding the 'earlier' ones.
   - Also, ordinarily, a more specific rule will override a less-specific rule. So:

   ```
    a {
        /* css */
    }
   ```

   - Is normally overruled by:

   ```
     body div #elementID ul li a {
        /* css */
    }
   ```

8. **What is your prefered layout system: inline-block, floating + clearing, flex, grid, other? And why?**

   - I will prefered `inline-block`
   - Because It has been possible for a long time to create a grid of boxes that fills the browser width and wraps nicely (when the browser is resized), by using the float property. However, the `inline-block` value of the display property makes this even easier. `inline-block` elements are like inline elements but they can have a width and a height.

9. **Are negative margins legal and what do they do (margin: -20px)?**

   - Some how its legal.
   - controls the amount of space between an element's border and surrounding elements. If you set an element's margin to a negative value, the element will grow larger.

10. **If a `<div/>` has no margin or other styling and a `<p/>` tag inside of it has a margin top of some kind, the margin from the `<p/>` tag will show up on the div instead (the margin will show above the div not inside of it), why is this? What are the different things that can be done to prevent it?**
    - I think we should add `position: relative;` to the `<div/>`

## CSS:

11. **What technologies do you use to unit test your react components?**

    - Jest and enzyme mostly

12. **Are there any pitfalls associated with this technology that have caused you difficulty in the past?**

    - No

13. **How do you test in your unit tests to see if the correct properties are being passed to child components.**

    - Here's an example which I did in my recent project

    ```
    import * as React from "react";
    import { configure, shallow, ShallowWrapper } from "enzyme";
    import * as ReactSixteenAdapter from "enzyme-adapter-react-16";
    configure({ adapter: new ReactSixteenAdapter() });

    import {
        FixerGridItem,
        IGridHeaderAvatarElement,
        IGridHeaderTextElement,
        IGridFooterElement,
        IGridButtonDetails,
        IGridStatus,
    } from "./FixerGridItem";
    import * as Style from "./FixerGridItem.css";
    import { OptionsMenuItem, OptionsMenu } from "../../OptionsMenu/OptionsMenu";
    import {
        StatusMenuItems,
        InvoiceStatusDropdown,
    } from "../../InvoicesList/InvoiceStatusDropdown/InvoiceStatusDropdown";
    import { InvoiceStatusType } from "../../../models/InvoicesModel";
    import { FixerButtonStyling, FixerButtonSizing, FixerButton } from "../FixerButton/FixerButton";

    import "app/utils";
    import { FixerProgressBar } from "../FixerProgressBar/FixerProgressBar";
    import { FormattedMessage } from "react-intl";
    import Avatar from "react-avatar";

    describe("FixerGridItem", () => {
        const sampleItemId: string = "sample-id";
        const sampleHeaderAvatarContainer: IGridHeaderAvatarElement = {
            displayNameAvatar: true,
            displayNameonAvatar: "displayNameonAvatar",
            tagIcon: "tag-icon-src",
        };
        const sampleHeaderTextElement: IGridHeaderTextElement = {
            oneLineDesignationDisplay: true,
            titleField: "title",
        };
        const sampleLeftContainer: IGridFooterElement = {
            count: 12,
            name: "Subscriptions",
        };
        const sampleRightContainer: IGridFooterElement = {
            count: 1526,
            name: "Billing Amount",
        };
        const sampleOptionsMenuItems: OptionsMenuItem[] = [
            {
                label: "sample-label-0",
                name: "sample-name-0",
                onClick: jest.fn(),
            },
            {
                label: "sample-label-1",
                name: "sample-name-1",
                onClick: jest.fn(),
            },
        ];
        const sampleButtonsDetails: IGridButtonDetails = {
            icon: "icon-src",
            text: "text",
            width: 150,
            style: FixerButtonStyling.Blue,
            size: FixerButtonSizing.Medium,
            onClick: jest.fn(),
        };
        const sampleGridStatus: IGridStatus = {
            status: InvoiceStatusType.Draft,
            width: 200,
            height: 200,
            fontSize: 16,
        };
        const sampleGridStatusOptions: StatusMenuItems[] = [
            {
                label: "label-0",
                name: "name-0",
                icon: "icon-0",
            },
            {
                label: "label-1",
                name: "name-1",
                icon: "icon-1",
            },
        ];
        const sampleOnStatusChange = jest.fn();
        const sampleIsStatusLoading: boolean = false;
        const sampleShowProgressbar: boolean = true;
        const sampleProgress: number = 20;
        const sampleOnItemClick = jest.fn();

        const testElement: JSX.Element = (
            <FixerGridItem
                itemId={sampleItemId}
                headerAvatarContainer={sampleHeaderAvatarContainer}
                headerTextElement={sampleHeaderTextElement}
                leftContainer={sampleLeftContainer}
                rightContainer={sampleRightContainer}
                isLoading={false}
                optionsMenuItems={sampleOptionsMenuItems}
                buttonsDetails={sampleButtonsDetails}
                gridStatus={sampleGridStatus}
                gridStatusOptions={sampleGridStatusOptions}
                onStatusChange={sampleOnStatusChange}
                isStatusLoading={sampleIsStatusLoading}
                showProgessbar={sampleShowProgressbar}
                progress={sampleProgress}
                onItemClick={sampleOnItemClick}
            />
        );
        const shallowWrapper: ShallowWrapper<FixerGridItem.IProps, FixerGridItem.IState> = shallow(
            testElement
        );

        test("snapshot", () => {
            expect(shallowWrapper).toMatchSnapshot();
        });

        test("props.onItemClick: The onItemClick function should be raised if user click the button in element", () => {
            expect(sampleOnItemClick).toHaveBeenCalledTimes(0);
            shallowWrapper.simulate("click");
            expect(sampleOnItemClick).toHaveBeenCalledTimes(1);

            expect(sampleOnItemClick.mock.calls[sampleOnItemClick.mock.calls.length - 1][0]).toEqual(
                sampleItemId
            );
        });

        test("props.showProgessbar: The progress element should show only if props.showProgessbar is true", () => {
            shallowWrapper.setProps({
                showProgessbar: true,
            });

            expect(shallowWrapper.find(`.${Style.progressContainer}`).length).toEqual(1);
            expect(
                shallowWrapper
                    .find(`.${Style.progressContainer}`)
                    .find(FixerProgressBar)
                    .prop("percentage")
            ).toEqual(sampleProgress);

            shallowWrapper.setProps({
                showProgessbar: false,
            });

            expect(shallowWrapper.find(`.${Style.progressContainer}`).length).toEqual(0);
        });

        test("props.progress: The percentage of FixerProgressBar props and props.progress should be equal", () => {
            shallowWrapper.setProps({
                showProgessbar: true,
            });

            expect(
                shallowWrapper
                    .find(`.${Style.progressContainer}`)
                    .find(FixerProgressBar)
                    .prop("percentage")
            ).toEqual(sampleProgress);
        });

        describe("props.buttonsDetails: Validation of showing condition, props, and onClick function", () => {
            test("showing condition", () => {
                expect(
                    shallowWrapper.find(`.${Style.gridViewButton}`).find(FixerButton).length
                ).toEqual(1);
                shallowWrapper.setProps({
                    buttonsDetails: undefined,
                });
                expect(
                    shallowWrapper.find(`.${Style.gridViewButton}`).find(FixerButton).length
                ).toEqual(0);
            });

            test("props", () => {
                shallowWrapper.setProps({
                    buttonsDetails: sampleButtonsDetails,
                });
                const targetButton = shallowWrapper.find(`.${Style.gridViewButton}`).find(FixerButton);
                expect(targetButton.prop("icon")).toEqual(sampleButtonsDetails.icon);
                expect(targetButton.prop("text")).toEqual(sampleButtonsDetails.text);
                expect(targetButton.prop("width")).toEqual(sampleButtonsDetails.width);
                expect(targetButton.prop("style")).toEqual(sampleButtonsDetails.style);
                expect(targetButton.prop("size")).toEqual(sampleButtonsDetails.size);
            });

            test("onClick function", () => {
                shallowWrapper.setProps({
                    buttonsDetails: sampleButtonsDetails,
                });
                const targetButton = shallowWrapper.find(`.${Style.gridViewButton}`).find(FixerButton);

                expect(sampleButtonsDetails.onClick).toHaveBeenCalledTimes(0);
                targetButton.simulate("click");
                expect(sampleButtonsDetails.onClick).toHaveBeenCalledTimes(1);
            });
        });

        test("props.onStatusChange, props.isStatusLoading, props.gridStatus, props.gridStatusOptions: InvoiceStatusDropdown's prop and several props should be equal", () => {
            const targetElement = shallowWrapper.find(InvoiceStatusDropdown);
            expect(targetElement.length).toEqual(1);

            expect(targetElement.prop("menuItems")).toEqual(sampleGridStatusOptions);
            expect(targetElement.prop("selectedOption")).toEqual(sampleGridStatus.status);
            expect(targetElement.prop("isLoading")).toEqual(sampleIsStatusLoading);
            expect(targetElement.prop("onSelect")).toEqual(sampleOnStatusChange);

            shallowWrapper.setProps({
                gridStatus: undefined,
            });

            expect(shallowWrapper.find(InvoiceStatusDropdown).length).toEqual(0);
        });

        test("props.optionsMenuItems: The optionMenuItems in OptionsMenu props and props.optionsMenuItems should be equal", () => {
            expect(shallowWrapper.find(OptionsMenu).prop("optionMenuItems")).toEqual(
                sampleOptionsMenuItems
            );
        });

        test("props.leftContainer: Contents in FormattedMessage and leftContainer.name should be equal", () => {
            shallowWrapper.setProps({
                leftContainer: {
                    count: 123,
                    name: "name",
                    currencyVal: true,
                },
            });

            const formattedMessage = shallowWrapper
                .find(`.${Style.subscriptionDetails}`)
                .find(FormattedMessage);
            expect(formattedMessage.prop("id")).toEqual("name");
            expect(formattedMessage.prop("defaultMessage")).toEqual("name");
        });

        test("props.rightContainer: Contents in FormattedMessage and rightContainer.name should be equal", () => {
            shallowWrapper.setProps({
                rightContainer: {
                    count: 123,
                    name: "name",
                    currencyVal: true,
                },
            });

            const formattedMessage = shallowWrapper
                .find(`.${Style.subscriptionDetails}`)
                .find(FormattedMessage);
            expect(formattedMessage.prop("id")).toEqual("name");
            expect(formattedMessage.prop("defaultMessage")).toEqual("name");
        });

        describe("props.headerTextElement", () => {
            test("titleField", () => {
                shallowWrapper.setProps({
                    headerTextElement: {
                        oneLineDesignationDisplay: false,
                        titleField: "titleField",
                        leftDesignation: "",
                    },
                });
                expect(shallowWrapper.find(`.${Style.mainTitle}`).text()).toEqual("titleField");
            });

            test("oneLineDesignationDisplay: true", () => {
                shallowWrapper.setProps({
                    headerTextElement: {
                        oneLineDesignationDisplay: true,
                        titleField: "",
                        oneLineDesignation: "oneLineDesignation",
                    },
                });
                expect(shallowWrapper.find(`.${Style.singleDesignation}`).length).toEqual(1);
                expect(shallowWrapper.find(`.${Style.singleDesignation}`).text()).toEqual(
                    "oneLineDesignation"
                );
            });

            test("oneLineDesignationDisplay: false", () => {
                shallowWrapper.setProps({
                    headerTextElement: {
                        oneLineDesignationDisplay: false,
                        titleField: "",
                        leftDesignation: "leftDesignation",
                        rightDesignation: "rightDesignation",
                        oneLineDesignation: "",
                    },
                });
                expect(
                    shallowWrapper
                        .find(`.${Style.team}`)
                        .find(FormattedMessage)
                        .prop("id")
                ).toEqual("leftDesignation");
                expect(
                    shallowWrapper
                        .find(`.${Style.team}`)
                        .find(FormattedMessage)
                        .prop("defaultMessage")
                ).toEqual("leftDesignation");
                expect(shallowWrapper.find(`.${Style.teamEmployee}`).text()).toEqual(
                    "rightDesignation"
                );
            });
        });

        describe("props.headerAvatarContainer", () => {
            test("hasBackground", () => {
                shallowWrapper.setProps({
                    headerAvatarContainer: {
                        ...sampleHeaderAvatarContainer,
                        hasBackground: true,
                    },
                });

                expect(
                    shallowWrapper.find(`.${Style.tagItemIcon}`).hasClass(Style.hasBackground)
                ).toBeTruthy();

                shallowWrapper.setProps({
                    headerAvatarContainer: {
                        ...sampleHeaderAvatarContainer,
                        hasBackground: false,
                    },
                });

                expect(
                    shallowWrapper.find(`.${Style.tagItemIcon}`).hasClass(Style.hasBackground)
                ).toBeFalsy();
            });

            test("headerAvatarContainer.customAvatar is true", () => {
                shallowWrapper.setProps({
                    headerAvatarContainer: {
                        ...sampleHeaderAvatarContainer,
                        customAvatar: true,
                    },
                });
                expect(
                    shallowWrapper.find(`.${Style.gridAvatarContainer}`).find(`.${Style.gridAvatar}`)
                        .length
                ).toEqual(1);
            });

            test("headerAvatarContainer.customAvatar is false and headerAvatarContainer.displayNameAvatar is true", () => {
                shallowWrapper.setProps({
                    headerAvatarContainer: {
                        ...sampleHeaderAvatarContainer,
                        customAvatar: false,
                        displayNameAvatar: true,
                        displayNameonAvatar: "displayNameonAvatar",
                    },
                });
                const avatar = shallowWrapper.find(Avatar);
                expect(avatar.prop("name")).toEqual("displayNameonAvatar");
            });

            test("headerAvatarContainer.customAvatar is false and headerAvatarContainer.displayNameAvatar is false", () => {
                shallowWrapper.setProps({
                    headerAvatarContainer: {
                        ...sampleHeaderAvatarContainer,
                        customAvatar: false,
                        displayNameAvatar: false,
                        centerIcon: "centerIcon",
                    },
                });
                const avatar = shallowWrapper.find(Avatar);
                expect(avatar.prop("src")).toEqual("centerIcon");
            });
        });
    });

    ```
