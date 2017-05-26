# GenKit
<span style="font-size:0.6em; color:gray">YAML -> Code</span> |
<span style="font-size:0.6em; color:gray">See <a href="https://github.com/SmallPlanetSwift/GenKit/" target="_blank">GenKit</a> on GitHub for details.</span>

---

## Why GenKit?
<span style="color:#29B8EB">Safe</span> |
<span style="color:#29B8EB">Lazy</span>

We don't usually get to be lazy _and_ safe

+++

## Safe

* Define data in human-writable YAML files
* Templates transform data into whatever
* Single source of constants
* Parity between platforms

+++

## Lazy

* Automate repetetive code generation
* Allow non-developers to make changes without touching code

---

## Using GenKit
Build | Run

+++

## Build

* Written in Swift
* Built with Swift Package Manager

</br>

```bash
swift build
```

+++

## Run

```bash
> .build/debug/gen

Usage: .build/debug/gen [options]
  -i, --input:
      Input yaml file
  -t, --template:
      Stencil template file
  -s, --stencil:
      Use Stencil instead of Mustache template
  -o, --output:
      Output file (writes to stdout if not provided)
  -c, --compare:
      Files to compare modification dates against (multiple values separated by space)
```

<span style="font-size:0.8em; color:gray">Without options, gen prints usage</span>

+++

## Run

```bash
gen -i input.yaml -t template.mustache
```

<span style="font-size:0.8em; color:gray">Processes data in **input.yaml** using the Mustache template **template.mustache**, sends output to stdout.</span>


## Run

```bash
gen -i input.yaml -t template.stencil -s
```

<span style="font-size:0.8em; color:gray">Processes data in **input.yaml** using the Stencil template **template.stencil** because of -s option.</span>

---

## Data

* Stored in YAML format
* Top-level must be a dictionary
* Otherwise anything goes

+++

## Sample

```yaml
name: AnalyticsKeys
package: com.smallplanet.android.project.analytics
groups:

# Core Events

  - name: Screens
    strings:
      - var: day
        string: Day
      - var: calendar
        string: Calendar
      - var: settings
        string: Settings
      - var: resource
        string: Resource
```

+++

## YAML Benefits

* Functionally equivalent to JSON
* Easier to read/write
* Comment: can add comments


---

## Template Choice

<a href="https://github.com/IBM-Swift/GRMustache.swift" target="_blank">Mustache</a> |
<a href="https://github.com/kylef/Stencil" target="_blank">Stencil</a>

+++

## Mustache

* Default template engine
* Closely follows <a href="http://mustache.github.io" target="_blank">Mustache</a> standard
* Uses IBM's actively developed fork
* <a href="https://github.com/IBM-Swift/GRMustache.swift" target="_blank">github.com/IBM-Swift/GRMustache.swift</a>

+++

## Stencil

* Optional system accessed with -s or --stencil option
* <a href="https://github.com/kylef/Stencil.git" target="_blank">github.com/kylef/Stencil</a>
---

## Integration/Automation
