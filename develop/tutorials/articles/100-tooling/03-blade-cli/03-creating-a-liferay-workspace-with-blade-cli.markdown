# Creating a Liferay Workspace with Blade CLI [](id=creating-a-liferay-workspace-with-blade-cli)

In this tutorial, you'll learn how to generate a Liferay Workspace using Blade
CLI. The Blade CLI tool you installed in the
[Installing Blade CLI](/develop/tutorials/-/knowledge_base/7-1/installing-blade-cli)
section provides many different commands to help build and customize Liferay
projects. The first thing you should do before building and customizing projects
is create a Liferay Workspace. You can use Blade CLI to generate a Gradle or
Maven based workspace. For more information on managing a Liferay Workspace
built with Maven, see the
[Maven Workspace](/develop/tutorials/-/knowledge_base/7-1/maven-workspace)
tutorial.

Your workspace is the home for all your custom Liferay projects. Navigate to the
folder where you want your workspace and run the following command to build a
Gradle based workspace:

    blade init [WORKSPACE_NAME]

To create a Maven based workspace, run this instead:

    blade init -b maven [WORKSPACE_NAME]

Initializing a workspace requires no downloading or access to the internet.

If you have a Plugins SDK and are looking to migrate to Liferay Workspace using
Blade CLI, navigate to your Plugins SDK root folder and run
the following command:

    blade init -u

This command builds a workspace and automatically adds and configures your
current Plugins SDK environment for use inside the workspace. 
See the
[Configuring a Plugins SDK in Your Workspace](/develop/tutorials/-/knowledge_base/7-0/creating-a-liferay-workspace-with-blade-cli#configuring-a-plugins-sdk-in-your-workspace)
section for more details on the `init -u` command. See the
[Using a Plugins SDK From Your Workspace](/develop/tutorials/-/knowledge_base/7-0/configuring-a-liferay-workspace#using-a-plugins-sdk-from-your-workspace)
section for more information on how to use a Plugins SDK from within a
workspace.

Once your workspace is generated, look at its folder structure. Several folders
and build/properties files were autogenerated: 

- `configs`
- `gradle`
- `modules`
- `themes`
- `wars`
- `build.gradle`
- `gradle.properties`
- `gradle-local.properties`
- `gradlew`
- `settings.gradle`

The build/properties files included in your workspace's root directory sets your
workspace's Gradle properties and facilitates the build processes of your
modules. You can learn more about these generated files/folders in the
[Configuring a Liferay Workspace](/develop/tutorials/-/knowledge_base/7-1/configuring-a-liferay-workspace)
tutorial. You'll learn about how to use these folders and properties files
throughout the next few tutorials. 

Next you'll learn about generating and using a @product@ instance from within
your workspace.

## Running a Liferay Instance from Your Workspace [](id=running-a-liferay-instance-from-your-workspace)

As discussed in the 
[Configuring a Liferay Workspace](/develop/tutorials/-/knowledge_base/7-1/configuring-a-liferay-workspace#adding-a-liferay-bundle-to-a-workspace)
tutorial, Liferay Workspaces can generate and hold a Liferay Server. This lets
you build/test your plugins against a running Liferay instance. Once you've
properly generated and installed a Liferay server in your workspace, you can
begin using it with Blade CLI. To start your Liferay instance, run

    blade server start -b

This command starts your Liferay server in a separate window. You also have the
option to run your server in debug mode (`-d`).

Awesome! You have a built-in Liferay server in your workspace and can start the
server using Blade CLI.
