---
layout: default
title: Command Reference
abstract: "A guide to Meshery's CLI: mesheryctl"
permalink: reference/mesheryctl
redirect_from: reference/mesheryctl/commands/
type: Reference

---
## Categories and Command Structure

Meshery CLI commands are categorized by function, which are:

- `mesheryctl` - Global flags and CLI configuration
- `mesheryctl system` - Meshery Lifecycle and Troubleshooting
- `mesheryctl mesh` - Service Mesh Lifecycle & Configuration Management: provisioning and configuration best practices
- `mesheryctl perf` -  Service Mesh Performance Management: Workload and service mesh performance characterization
- `mesheryctl pattern` - Service Mesh Pattern Configuration & Management: Service mesh patterns and Open Application Model integration
- `mesheryctl filter` - Data Plane Intelligence: Registry and configuration of WebAssembly filters for Envoy (Coming soon!)


## Global Commands and Flags

<table>
<thead>
  <tr>
    <th>Command</th>
    <th>Subcommand</th>
    <th>Flag</th>
    <th>Function</th>
  </tr>
  {% assign command1 = site.data.mesheryctlcommands.cmds.global %}
    <tr>
      <td rowspan=6><a href="{{ site.baseurl }}/reference/mesheryctl/mesheryctl">{{ command1.name }}</a></td>
      <td></td>
      <td></td>
      <td>{{ command1.description }}</td>
    </tr>
    {% for subcommand_hash in command1.subcommands %}{% assign subcommand = subcommand_hash[1] %}
      <tr>
         <td><a href="{{ site.baseurl }}/reference/mesheryctl/mesheryctl/version">{{ subcommand.name }}</a></td>
         <td></td>
         <td>{{ subcommand.description }}</td>
      </tr>
      {% for flag_hash in command1.flags %}{% assign flag = flag_hash[1] %}
        <tr>
         <td></td>
         <td>{{ flag.name }}</td>
         <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
    {% endfor %}
</thead>
</table>

## Meshery Lifecycle Management and Troubleshooting

Installation, troubleshooting and debugging of Meshery and its adapters.

<table>
<thead>
  <tr>
    <th>Main Command</th>
    <th>Arguments</th>
    <th>Flag</th>
    <th>Function</th>
  </tr>
  {% assign command2 = site.data.mesheryctlcommands.cmds.system %}
    <tr>
      <td rowspan=18><a href="{{ site.baseurl }}/reference/mesheryctl/system">{{ command2.name }}</a></td>
      <td></td>
      <td></td>
      <td>{{ command2.description }}</td>
    </tr>
    {% for flag_hash in command2.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td></td>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand1 = command2.subcommands.start %}
      <tr>
        <td rowspan=4><a href="{{ site.baseurl }}/reference/mesheryctl/system/start">{{ subcommand1.name }}</a></td>
        <td></td>
        <td>{{ subcommand1.description }}</td>
      </tr>
    {% for flag_hash in subcommand1.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %} 
    {% assign subcommand2 = command2.subcommands.stop %} 
    <tr>
      <td rowspan=2><a href="{{ site.baseurl }}/reference/mesheryctl/system/stop">{{ subcommand2.name }}</a></td>
      <td></td>
      <td>{{ subcommand2.description }}</td>
    </tr>
    {% for flag_hash in subcommand2.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand3 = command2.subcommands.completion %}
    <tr>
      <td><a href="{{ site.baseurl }}/reference/mesheryctl/system/completion">{{ subcommand3.name }}</a></td>
      <td></td>
      <td>{{ subcommand3.description }}</td>
    </tr>
    {% for flag_hash in subcommand3.flag %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand4 = command2.subcommands.update %}
    <tr>
      <td rowspan=2><a href="{{ site.baseurl }}/reference/mesheryctl/system/update">{{ subcommand4.name }}</a></td>
      <td></td>
      <td>{{ subcommand4.description }}</td>
    </tr>
    {% for flag_hash in subcommand4.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}  
    {% assign subcommand5 = command2.subcommands.config %}
    <tr>
      <td rowspan=2><a href="{{ site.baseurl }}/reference/mesheryctl/system/config">{{ subcommand5.name }}</a></td>
      <td></td>
      <td>{{ subcommand5.description }}</td>
    </tr>
    {% for flag_hash in subcommand5.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand6 = command2.subcommands.reset %}
    <tr>
      <td><a href="{{ site.baseurl }}/reference/mesheryctl/system/reset">{{ subcommand6.name }}</a></td>
      <td></td>
      <td>{{ subcommand6.description }}</td>
    </tr>
    {% for flag_hash in subcommand6.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand7 = command2.subcommands.logs %}
    <tr>
      <td><a href="{{ site.baseurl }}/reference/mesheryctl/system/logs">{{ subcommand7.name }}</a></td>
      <td></td>
      <td>{{ subcommand7.description }}</td>
    </tr>
    {% for flag_hash in subcommand7.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand8 = command2.subcommands.restart %}
    <tr>
      <td rowspan=2><a href="{{ site.baseurl }}/reference/mesheryctl/system/restart">{{ subcommand8.name }}</a></td>
      <td></td>
      <td>{{ subcommand8.description }}</td>
    </tr>
    {% for flag_hash in subcommand8.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand9 = command2.subcommands.status %}
    <tr>
      <td><a href="{{ site.baseurl }}/reference/mesheryctl/system/status">{{ subcommand9.name }}</a></td>
      <td></td>
      <td>{{ subcommand9.description }}</td>
    </tr>
    {% for flag_hash in subcommand9.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}  

  {% assign command3 = site.data.mesheryctlcommands.cmds.system-channel %}
        <tr>
          <td rowspan=4><a href="{{ site.baseurl }}/reference/mesheryctl/system/channel">{{ command3.name }}</a></td>
          <td></td>
          <td></td>
          <td>{{ command3.description }}</td>
        </tr>
        {% for subcommand_hash in command3.subcommands %}{% assign subcommand = subcommand_hash[1] %}
          <tr>
            <td>{{ subcommand.name }}</td>
            <td></td>
            <td>{{ subcommand.description }}</td>
          </tr>
        {% endfor %}
    {% assign subcommand1 = command3.subcommands.view %}
    {% for flag_hash in subcommand1.flag %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign command4 = site.data.mesheryctlcommands.cmds.system-context %}
      <tr>
        <td rowspan=10><a href="{{ site.baseurl }}/reference/mesheryctl/system/context">{{ command4.name }}</a></td>
        <td></td>
        <td></td>
        <td>{{ command4.description }}</td>
      </tr>
      {% assign subcommand1 = command4.subcommands.create %}
        <tr>
          <td rowspan=4><a href="{{ site.baseurl }}/reference/mesheryctl/system/context/create">{{ subcommand1.name }}</a></td>
          <td></td>
          <td>{{ subcommand1.description }}</td>
        </tr>
      {% for flag_hash in subcommand1.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
      {% assign subcommand2 = command4.subcommands.delete %}
        <tr>
          <td><a href="{{ site.baseurl }}/reference/mesheryctl/system/context/delete">{{ subcommand2.name }}</a></td>
          <td></td>
          <td>{{ subcommand2.description }}</td>
        </tr>
      {% assign subcommand3 = command4.subcommands.view %}
        <tr>
          <td rowspan=3><a href="{{ site.baseurl }}/reference/mesheryctl/system/context/view">{{ subcommand3.name }}</a></td>
          <td></td>
          <td>{{ subcommand3.description }}</td>
        </tr>
      {% for flag_hash in subcommand3.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
      {% assign subcommand4 = command4.subcommands.switch %}
        <tr>
          <td rowspan=4><a href="{{ site.baseurl }}/reference/mesheryctl/system/context/switch">{{ subcommand4.name }}</a></td>
          <td></td>
          <td>{{ subcommand4.description }}</td>
        </tr>
      {% for flag_hash in subcommand4.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
</thead>
</table>

## Service Mesh Performance Management

<table>
<thead>
  <tr>
    <th>Main Command</th>
    <th>Arguments</th>
    <th>Flag</th>
    <th>Function</th>
  </tr>
  {% assign command5 = site.data.mesheryctlcommands.cmds.perf %}
    <tr>
      <td rowspan=18><a href="{{ site.baseurl }}/reference/mesheryctl/perf">{{ command5.name }}</a></td>
      <td></td>
      <td></td>
      <td>{{ command5.description }}</td>
    </tr>
    {% for flag_hash in command5.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td></td>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
  {% assign subcommand1 = command5.subcommands.apply %}
      <tr>
        <td rowspan=10><a href="{{ site.baseurl }}/reference/mesheryctl/perf/apply">{{ subcommand1.name }}</a></td>
        <td></td>
        <td>{{ subcommand1.description }}</td>
      </tr>
  {% for flag_hash in subcommand1.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
  {% endfor %}
  {% assign subcommand2 = command5.subcommands.list %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/perf/list">{{ subcommand2.name }}</a></td>
        <td></td>
        <td>{{ subcommand2.description }}</td>
      </tr>
  {% assign subcommand3 = command5.subcommands.view %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/perf/view">{{ subcommand3.name }}</a></td>
        <td></td>
        <td>{{ subcommand3.description }}</td>
      </tr>
</thead>
</table>


## Service Mesh Lifecycle and Configuration Management

<table>
<thead>
  <tr>
    <th>Main Command</th>
    <th>Command</th>
    <th>Flag</th>
    <th>Function</th>
  </tr>
  {% assign command6 = site.data.mesheryctlcommands.cmds.mesh %}
    <tr>
      <td rowspan=10><a href="{{ site.baseurl }}/reference/mesheryctl/mesh">{{ command6.name }}</a></td>
      <td></td>
      <td></td>
      <td>{{ command6.description }}</td>
    </tr>
    {% assign subcommand1 = command6.subcommands.validate %}
      <tr>
        <td rowspan=5><a href="{{ site.baseurl }}/reference/mesheryctl/mesh/validate">{{ subcommand1.name }}</a></td>
        <td></td>
        <td>{{ subcommand1.description }}</td>
      </tr>
      {% for flag_hash in subcommand1.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
    {% assign subcommand2 = command6.subcommands.deploy %}
      <tr>
        <td rowspan=4><a href="{{ site.baseurl }}/reference/mesheryctl/mesh/deploy">{{ subcommand2.name }}</a></td>
        <td></td>
        <td>{{ subcommand2.description }}</td>
      </tr>
      {% for flag_hash in subcommand2.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
        </tr>
      {% endfor %}
</thead>
</table>

## Service Mesh Pattern Configuration and Management

<table>
<thead>
  <tr>
    <th>Main Command</th>
    <th>Command</th>
    <th>Flag</th>
    <th>Function</th>
  </tr>
  {% assign command7 = site.data.mesheryctlcommands.cmds.pattern %}
    <tr>
      <td rowspan=12><a href="{{ site.baseurl }}/reference/mesheryctl/pattern">{{ command7.name }}</a></td>
      <td></td>
      <td></td>
      <td>{{ command7.description }}</td>
    </tr>
    {% for flag_hash in command7.flags %}{% assign flag = flag_hash[1] %}
      <tr>
        <td></td>
        <td>{{ flag.name }}</td>
        <td>{{ flag.description }}</td>
      </tr>
    {% endfor %}
    {% assign subcommand1 = command7.subcommands.list %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/pattern/list">{{ subcommand1.name }}</a></td>
        <td></td>
        <td>{{ subcommand1.description }}</td>
      </tr>
      {% for flag_hash in subcommand1.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td></td>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
      </tr>
      {% endfor %}
    {% assign subcommand2 = command7.subcommands.apply %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/pattern/apply">{{ subcommand2.name }}</a></td>
        <td></td>
        <td>{{ subcommand2.description }}</td>
      </tr>
      {% for flag_hash in subcommand2.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td></td>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
      </tr>
      {% endfor %}
    {% assign subcommand3 = command7.subcommands.view %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/pattern/view">{{ subcommand3.name }}</a></td>
        <td></td>
        <td>{{ subcommand3.description }}</td>
      </tr>
      {% for flag_hash in subcommand3.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td></td>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
      </tr>
      {% endfor %}
    {% assign subcommand4 = command7.subcommands.delete %}
      <tr>
        <td><a href="{{ site.baseurl }}/reference/mesheryctl/pattern/delete">{{ subcommand4.name }}</a></td>
        <td></td>
        <td>{{ subcommand4.description }}</td>
      </tr>
      {% for flag_hash in subcommand4.flags %}{% assign flag = flag_hash[1] %}
        <tr>
          <td></td>
          <td>{{ flag.name }}</td>
          <td>{{ flag.description }}</td>
      </tr>
      {% endfor %}
</thead>
</table>
