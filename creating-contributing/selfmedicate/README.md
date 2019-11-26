# Previewing Locally

If you've made changes to the NRE Labs curriculum and are looking to contribute them, you'll probably want to find a way to run them locally yourself before opening a pull request. The [selfmedicate](https://github.com/nre-learning/antidote-selfmedicate) tool is a way to get a local version of NRE Labs running on your own machine. This allows you to see how your lesson actually performs, before you open a Pull Request.

### Preparing the Environment

In the last section, you cloned your fork of the NRE Labs curriculum to your own machine. If this is still the working directory in your shell, navigate to the parent directory like so:

```text
cd ../
```

The important thing at this point is that your shell should currently be located at the parent directory of the NRE Labs curriculum. Next, clone and enter the selfmedicate repository:

```text
git clone https://github.com/nre-learning/antidote-selfmedicate
cd antidote-selfmedicate/
```

{% hint style="info" %}
**Please remember** that changes are being made to selfmedicate all the time. If you encounter issues, the very first thing you should try before you open an issue is to make sure you have the latest copy of this repository by doing a `git pull` on the master branch.
{% endhint %}



