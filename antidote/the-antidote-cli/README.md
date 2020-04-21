# The Antidote CLI

The Antidote platform also comes with a CLI tool called `antidote`, which is meant to be used primarily by curriculum authors to validate or create new curriculum content like lessons.

You can always find the latest release[ here](https://github.com/nre-learning/syringe/releases/latest), where pre-compiled binaries for Antidote have been posted. For convenience, shell commands for downloading the latest version of this tool on your system are below:

{% tabs %}
{% tab title="macOS" %}
```text
curl -Lo antidote.tar.gz https://github.com/nre-learning/antidote-core/releases/download/v0.6.0/antidote-darwin-amd64.tar.gz
tar xvzf antidote.tar.gz
./antidote -h
```
{% endtab %}

{% tab title="Windows \(x64\)" %}
```text
$ProgressPreference = 'SilentlyContinue'
Invoke-WebRequest https://github.com/nre-learning/antidote-core/releases/download/v0.6.0/antidote-windows-amd64.zip -O antidote.zip
Expand-Archive -Force -LiteralPath 'antidote.zip' -DestinationPath .
.\antidote.exe -h
```
{% endtab %}

{% tab title="Linux \(x64\)" %}
```text
curl -Lo antidote.tar.gz https://github.com/nre-learning/antidote-core/releases/download/v0.6.0/antidote-linux-amd64.tar.gz
tar xvzf antidote.tar.gz
./antidote -h
```
{% endtab %}
{% endtabs %}

Note that this will result in the `antidote` binary being made available in the current directory. You may wish to either add this directory to your PATH, or move the binary to one that already is. The remainder of this documentation will assume you've done this, so that you can simply run the command `antidote` from anywhere. You can of course instead run the binary via the relative path shown in the final command above if you wish, it will work fine the same way.



