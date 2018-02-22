# mvp_gismart
MVP + clean architecture template for Generamba from gismart team.  


**Generamba** is a code generator made for working with Xcode. Primarily it is designed to generate VIPER modules but it is quite easy to customize it for generation of any other classes (both in Objective-C and Swift).

### Key features

- Supports work with *.xcodeproj* files out of the box. All generated class files are automatically placed to specific folders and groups of Xcode project.
- Can generate both code itself and tests adding them to right targets.
- Based on work with [liquid-templates](https://github.com/Shopify/liquid) that have plain and readable syntax in comparison with templates for Xcode.
- It is very easy to create a new module: `generamba gen [MODULE_NAME] [TEMPLATE_NAME]`. You do not need to input a bunch of data each time because each project corresponds to only one configuration file that holds standard file system and Xcode-project pathes, names of targets, information about the author.

### Installation

> Ruby 2.2 or later version is required. To check your current Ruby version run this command in terminal:
```bash
$ ruby --version
```
Run the command `gem install generamba`.


### Usage
1. If in the project haven't Rambafile, run [`generamba setup`](https://github.com/rambler-digital-solutions/Generamba/wiki/Available-Commands#basic-generamba-configuration) in the project root folder. This command helps to create [Rambafile](https://github.com/rambler-digital-solutions/Generamba/wiki/Rambafile-Structure) that define all configuration needed to generate code. You can modify this file directly in future.
2. - Add template to Rambafile
```sh
### Templates
templates:
- {name: gismart_mvp, git: 'https://github.com/AlexParhimovich/mvp_gismart.git'}
```
3. Run [`generamba template install`](https://github.com/rambler-digital-solutions/Generamba/wiki/Available-Commands#template-installation). All the templates will be placed in the '/Templates' folder of your current project.
4. Run [`generamba gen [MODULE_NAME] gismart_mvp`](https://github.com/rambler-digital-solutions/Generamba/wiki/Available-Commands#module-generation) - It creates module with specific name from specific template.

