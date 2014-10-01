<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title>Nagios Alerting Plugin</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=EmulateIE8" />
    <meta content="Scroll Wiki Publisher" name="generator"/>
    <link type="text/css" rel="stylesheet" href="css/blueprint/liquid.css" media="screen, projection"/>
    <link type="text/css" rel="stylesheet" href="css/blueprint/print.css" media="print"/>
    <link type="text/css" rel="stylesheet" href="css/content-style.css" media="screen, projection, print"/>
    <link type="text/css" rel="stylesheet" href="css/screen.css" media="screen, projection"/>
    <link type="text/css" rel="stylesheet" href="css/print.css" media="print"/>
</head>
<body>
                <h1>Nagios Alerting Plugin</h1>
    <p>
            <img src="images_community/download/attachments/17958239/icon.png" alt="images_community/download/attachments/17958239/icon.png" class="confluence-embedded-image" />
        This plugin allows <strong class=" ">sending dynaTrace alerts to a Nagios server</strong> using passive checks. Alerts can be posted only remotely (when Nagios and dynaTrace is on different hosts) using the NSCA (NSCA daemon on the Nagios side and the NSCA client on the dynaTrace side).    </p>
    <div class="tablewrap">
        <table>
<thead class=" "></thead><tfoot class=" "></tfoot><tbody class=" ">    <tr>
            <td rowspan="1" colspan="1">
        <p>
Name    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<strong class=" ">Nagios Alerting Plugin (NEW)</strong>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Version    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
1.0.0 (2014.06.26)    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
dynaTrace Version    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
5.6    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Support    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="http://www.telvice.hu">Telvice Kft.</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Author    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
Bal&aacute;zs Bakai (balazs.bakai@telvice.hu)    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Author blog    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="http://www.seamplex.blogspot.hu">Seamplex</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Download    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
Plugin binary: <a href="attachments_172195850_1_hu.telvice.TelviceNagiosAlerting_1.0.0.jar">hu.telvice.TelviceNagiosAlerting_1.0.0.jar</a>    </p>
    <p>
Plugin script: <a href="attachments_172195851_1_dt_telvice_nagios.sh">dt_telvice_nagios.sh</a>    </p>
    <p>
Sample config file : <a href="attachments_122978649_1_send_nsca.cfg">send_nsca.cfg</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
License    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
    <span style="color: #000000;">
LGPL v3    </span>
    </p>
            </td>
        </tr>
</tbody>        </table>
            </div>
    <div class="section-2"  id="17958239_NagiosAlertingPlugin-Installation"  >
        <h2>Installation</h2>
<ul class=" "><li class=" ">    <p>
On the dynaTrace server side, import the plugin jar file and activate the plugin. Then, you need to add the Nagios Action Plugin in the 'Extended Actions' of each of the incidents you want to generate Nagios alerts for. You also need to install the nsca client (download here for <a href="http://exchange.nagios.org/directory/Addons/Passive-Checks/NSCA--2D-Nagios-Service-Check-Acceptor/details">Linux</a> or <a href="http://exchange.nagios.org/directory/Addons/Passive-Checks/NSCA-Win32-Client/details">Win32</a>) on the dynaTrace server.    </p>
</li></ul><ul class=" "><li class=" ">    <p>
On the Nagios side, you need to declare the host and the services which you will generate alerts for. The host is arbitrary as you will be able to configure it for each alert you will generate from dynaTrace. The service description on the other hand must match the name of the incident that will trigger the alert.    </p>
</li></ul>    <p>
    </p>
    <p>
<strong class=" ">Incident Configuration</strong>    </p>
    <p>
Important to set up the execution list to: <strong class=" ">on incident begin and end</strong>, so dynaTrace can inform Nagios when the incidents end.    </p>
    <p>
            <img src="images_community/download/attachments/17958239/telvice_nagios1.jpg" alt="images_community/download/attachments/17958239/telvice_nagios1.jpg" class="confluence-embedded-image image-left" />
             </p>
    <p>
<strong class=" ">Plugin Script Location</strong>    </p>
    <p>
    <span style="color: #000000;">
Setup dt_telvice_nagios.sh unix script location.     </span>
    <span style="color: #000000;">
You should copy this script to this location on the dynaTraceServer host.    </span>
    </p>
    <p>
    <span style="color: #000000;">
     </span>
<br/>            <img src="images_community/download/attachments/17958239/telvice_nagios2.jpg" alt="images_community/download/attachments/17958239/telvice_nagios2.jpg" class="confluence-embedded-image" />
             </p>
    <p>
<strong class=" ">Plugin Script Parameters</strong>    </p>
    <p>
Setup these variables: NAGIOS_SERVER, NAGIOS_PORT, NAGIOS_BIN, NAGIOS_CFG in the dt_telvice_nagios.sh script.    </p>
    <p>
            <img src="images_community/download/attachments/17958239/telvice_nagios3.jpg" alt="images_community/download/attachments/17958239/telvice_nagios3.jpg" class="confluence-embedded-image" />
            </p>
    <p>
<strong class=" "><br/></strong>    </p>
    <p>
<strong class=" ">Nagios Service/Host configuration</strong>    </p>
    <div class="confbox programlisting">
                <div class="content">
        <pre><code># HOST DEFINITION
define host {
    use                  linux-server
    host_name            hegarlinux.dynatrace.local       ; MATCH THE HOSTNAME IN THE ALERT RULE DEFINITION
    alias                dynatrace-server
    address              127.0.0.1
}
# SERVICE TEMPLATE DEFINITION
# Template for the service : dynaTrace alerts from the command file
define service {
        name                       passive_checkservice
        use                        generic-service
        active_checks_enabled      0
        passive_checks_enabled     1
        normal_check_interval      1
        check_period               24x7
        check_interval             1
        retry_interval             1
        }
# SERVICE DEFINITION
# Define each dynaTrace alert that we want to be processed by Nagios
define service {
        use                        passive_checkservice
        host_name                  hegarlinux.dynatrace.local       ; MATCH THE HOST DEFINED EARLIER
        service_description        Warning: LastMinute Search   ; MATCH THE IINCIDENT NAME
        register                   1
        check_command              check_ping             ;not used  but mandatory command
}</code></pre>
        </div>
    </div>
    <p>
    </p>
    <p>
<strong class=" ">Nagios Overview</strong><br/>            <img src="images_community/download/attachments/17958239/Nagios.PNG" alt="images_community/download/attachments/17958239/Nagios.PNG" class="confluence-embedded-image" />
            </p>
    <p>
    </p>
    <p>
    </p>
    <p>
    </p>
    <div class="tablewrap">
        <table>
<thead class=" "></thead><tfoot class=" "></tfoot><tbody class=" ">    <tr>
            <td rowspan="1" colspan="1">
        <p>
Name    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<strong class=" ">Nagios Alerting Plugin (    <span style="color: #ff0000;">
not supported, old version    </span>
)</strong>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Version    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
1.0.0    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
dynaTrace Version    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
3.0.1    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Author    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
Alain H&eacute;la&iuml;li (<a href="mailto:alain.helaili@compuware.com">alain.helaili@compuware.com</a>)    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
Download    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
Plugin binary : <a href="attachments_122978648_1_com.dynatrace.plugins.nagios_1.1.0.jar">com.dynatrace.plugins.nagios_1.1.0.jar</a><br/>Sample config file : <a href="attachments_122978649_1_send_nsca.cfg">send_nsca.cfg</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
License    </p>
            </td>
                <td rowspan="1" colspan="1">
        <p>
<a href="attachments_5275722_2_dynaTraceBSD.txt">dynaTrace BSD</a>    </p>
            </td>
        </tr>
    <tr>
            <td rowspan="1" colspan="1">
        <p>
    <span style="color: #000000;">
Known problems    </span>
    </p>
            </td>
                <td rowspan="1" colspan="1">
    <ul class=" "><li class=" ">    <p>
The sent hostname for Nagios is the host of the dynaTraceServer not the host of the alerting agent    </p>
</li><li class=" ">    <p>
Does not send &quot;ok&quot; notification to Nagios when the incident ends    </p>
</li><li class=" ">    <p>
This plugin not supported anymore    </p>
</li></ul>            </td>
        </tr>
</tbody>        </table>
            </div>
    <p>
    </p>
    <p>
    </p>
    <p>
    </p>
    </div>
            </div>
        </div>
        <div class="footer">
        </div>
    </div>
</body>
</html>
