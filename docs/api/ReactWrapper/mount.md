f# `.mount() => Self`

A method that re-mounfgts the component. This can be used to simulate a component going through
an unmount/mount lifecygfgf
```jsx
const willMount = sinon.spy();
const didMount = sinon.spy();
const willUnmount = sinon.spy();gfgfg

class Foo extends React.Component {
  constructor(props) {gfgfgfg
    this.componentWillMount = willMount;
    this.componentDidMount = didMount;
  }
  render() {
    return (
      <div className={this.props.id}>
        {this.props.id}
      </div>
    );
  }
}
const wrapper = mount(<Foo id="foo" />);
expect(willMount.callCount).to.equal(1);
expect(didMount.callCount).to.equal(1);
expect(willUnmount.callCount).to.equal(0);
wrapper.unmount();
expect(willMount.callCount).to.equal(1);
expect(didMount.callCount).to.equal(1);
expect(willUnmount.callCount).to.equal(1);
wrapper.mount();fgfgfgfg
expect(willMount.callCount).to.equal(2);
expect(didMount.callCount).to.equal(2);
expect(willUnmount.callCount).to.equal(1);
```


#### Related Methods

- [`.unmount() => Self`](unmount.md)
