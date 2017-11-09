# card-hello-world
This is a sample Channels-compliant card design.

For more information about creating Channels cards, go to [ChannelsNetwork/channels-card-cli](https://github.com/ChannelsNetwork/channels-card-cli).

### [bower.json](https://github.com/ChannelsNetwork/card-hello-world/blob/master/bower.json)

Every Channels card project must a bower.json file which defines the project and its dependencies.  When developing your card, use [bower](https://bower.io/) to manage your package and declare all of your dependencies.

In bower.json, the **main** property must refer to the HTML file that contains your web component definitions.  Without this, Channels won't know what to import before using your card.  In most cases, this file should be named so as
to match your project.  In this case, it is **card-hello-world.html**.

### [channels-component.json](https://github.com/ChannelsNetwork/card-hello-world/blob/master/channels-component.json)

Every Channels card project must contain a channels-component.json file.  This extends the bower.json file with additional Channels-specific properties.  If you want to charge a royalty to publishers using your card, the **developerFraction** should be a number between 0 and 1 representing the fraction of the card price that will be paid to the developer.  The **developerAddress** is the address string associated with the Channels account to be paid these royalties.  You can find your account address on your Account page in Channels.

### [card-hello-world.html](https://github.com/ChannelsNetwork/card-hello-world/blob/master/card-hello-world.html)

This is the key file that defines this card and is the one referenced as **main**  in the bower.json file.  We define both the composer component and the viewer component within this one file.  If you prefer to separate these components, you can using import directives at the top of this file to refer to separate files containing your component definitions.

It is not required that you base your components on [Polymer](https://www.polymer-project.org/) but we do this here for convenience.  The only requirement is that your composer and viewer definitions can be imported from an HTML file, that each defines a corresponding web component, and that these web components have properties and fire events accordingly to the Channels card specifications.

In this hello-world example, the composer component is trivial.  It contains a text input where the user who is composing the card will enter some text.  The viewer displays information from the context provided to it.  In these examples, we use Polymer data binding but, again, that is not mandatory.

### [index.html](https://github.com/ChannelsNetwork/card-hello-world/blob/master/index.html) 

This file and the **demo** folder is added by the channels-card scaffolding. These are not required as part of the Channels component.  These are used by **polymer serve** so that you can try out your components before publishing.

### [icon.html](https://github.com/ChannelsNetwork/card-hello-world/blob/master/icon.png)

This is referenced in **channel-component.json** as **iconUrl**.  This is the icon used by Channels when displaying the card to help consumers know what kind of card they will be opening.  For your card, you should replace this with a 16x16 black-and-white image that is appropriate to your card type.