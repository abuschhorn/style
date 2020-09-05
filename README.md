# shop-401 React/JSX Style Guide

Introduction

## Table of Contents

  1. [Basic Rules](#basic-rules)
  1. [Class vsfunctional](#class-vs-reactcreateclass-vs-stateless)
  1. [Mixins](#mixins)
  1. [Naming](#naming)
  1. [Declaration](#declaration)
  1. [Alignment](#alignment)
  1. [Quotes](#quotes)
  1. [Spacing](#spacing)
  1. [Props](#props)
  1. [Refs](#refs)
  1. [Parentheses](#parentheses)
  1. [Tags](#tags)
  1. [Methods](#methods)
  1. [Ordering](#ordering)
  1. [`isMounted`](#ismounted)

## Basic Rules

  - Only include one React component per file.
    - However, multiple [Stateless, or Pure, Components](https://facebook.github.io/react/docs/reusable-components.html#stateless-functions) are allowed per file. eslint: [`react/no-multi-comp`](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-multi-comp.md#ignorestateless).
  - Always use JSX syntax.
  - Do not use `React.createElement` unless you’re initializing the app from a file that is not JSX.
  - [`react/forbid-prop-types`](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/forbid-prop-types.md) will allow `arrays` and `objects` only if it is explicitly noted what `array` and `object` contains, using `arrayOf`, `objectOf`, or `shape`.

## Class vs Functional React(Hook)

  - class

    ```jsx
    // bad
    const Product = React.createClass({
      // ...
      render() {
        return <div>{this.state.hello}</div>;
      }
    });

    // good
    class Product extends React.Component {
      // ...
      render() {
        return <div>{this.state.hello}</div>;
      }
    }
    ```

    Functional

    ```jsx
    // bad (relying on function name inference is discouraged)
    const Listing = ({ hello }) => (
      <div>{hello}</div>
    );

    // good
    function Listing(props) {
    const {hello} = props
      return <div>{hello}</div>;
    }
    ```
