# sliding-navbar

A little component for creating a smooth sliding navbar for your application.

![alt text](/preview/sliding-navbar.gif)

## Installation

`npm install sliding-navbar`

Import it into an existing component:
```
<script>
  import SlidingNavbar from 'sliding-navbar'

  export default {
    components: { SlidingNavbar },

    ...
  }
</script>
```

## Usage

```
<sliding-navbar>
  // your html goes here
</sliding-navbar>
```

**Note**
> This is just a slot, put whatever you want inside

## More controll

This is a list of props you can override to fit your needs

> nav-height: default: 80 - type: Number (px)

> duration: default: 200 - type: Number (ms)

> trigger-at: default: 80 - type: Number (px)


## Example

```
<sliding-navbar
  :nav-height="100"
  :duration="300"
  :trigger-at="200"
>
  ...
</sliding-navbar>
```

