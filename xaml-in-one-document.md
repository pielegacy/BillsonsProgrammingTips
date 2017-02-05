# XAML In One Document

> A sick as guide by Alex Billson

## XAML Markup

- Looks very similar to HTML styling, used to do the **View** side of your application.
- Works like HTML, is hierarchical in its structure.
- XAML has lots of equivalents across multiple implementations so don't be worried
if you can't find it.
- Visual Studio allows you to have a bunch of XAML templates and also includes a 
drag and drop designer for easily rendering your pages
- Every .xaml file has a C# file behind it
    ```
        MainPage.xaml
            -> MainPage.xaml.cs
        ```
    - The idea for this structure is that we define the visual layout and styles of our pages using XAML
    and the interaction and logic with C#
- A XAML element usually looks like the following

    ```xml
    <Element x:Name="ElementName" Property="Value" AnotherProperty="AnotherValue" EventHandler="Event"/>
    ```
- Basic Parts of an Element:
    - Element
        - The actual XAML element
    - Property
        - An attribute of the XAML element
        - For every XAML property there is an equivalent C# property you can reference in the backend code
        - Are paired with an associated value, always within quotes
    - x:Name
        - A special identifier given to XAML elements, allows you to reference them in the backend C# code
        - Like an id in HTML, must be unique
        - For example
            - Say we wanted to change the text of the following XAML element:

                ```xml
                <TextBlock x:Name="MainText" Text="Test"/>
                ```
            - We would refer to it in the backend C# as:

                ```csharp
                MainText.Text = "New Text";
                ```
    - Events
        - Events are called when an action happens to an element
        - Different elements have different Events
        - The code for an event is in the XAML pages .cs file