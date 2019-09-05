<script>

    // Specific to styleguide
    import Sample from '../components/Styleguide/Sample.svelte';
    import Component from '../components/Styleguide/Component.svelte';
    import Toc from '../components/Styleguide/Toc.svelte';

    // General UI
    import Alert from '../components/UI/Alert.svelte';
    import AlertStack from '../components/UI/AlertStack.svelte';
    import Blankslate from '../components/UI/Blankslate.svelte';
    import Box from '../components/UI/Box.svelte';
    import Button from '../components/UI/Button.svelte';
    import ButtonToolbar from '../components/UI/ButtonToolbar.svelte';
    import Content from '../components/UI/Content.svelte';
    import FormGroup from '../components/UI/FormGroup.svelte';
    import FormGroupLayout from '../components/UI/FormGroupLayout.svelte';
    import GridItem from '../components/UI/GridItem.svelte';
    import GridLayout from '../components/UI/GridLayout.svelte';
    import Icon from '../components/UI/Icon.svelte';
    import Input from '../components/UI/Input.svelte';
    import InputColor from '../components/UI/InputColor.svelte';
    import InputNumber from '../components/UI/InputNumber.svelte';
    import Label from '../components/UI/Label.svelte';
    import NavBar from '../components/UI/NavBar.svelte';
    import Panel from '../components/UI/Panel.svelte';
    import PanelBody from '../components/UI/PanelBody.svelte';
    import PanelHeader from '../components/UI/PanelHeader.svelte';
    import PanelRow from '../components/UI/PanelRow.svelte';
    import Select from '../components/UI/Select.svelte';
    import Spacer from '../components/UI/Spacer.svelte';
    import Toolbar from '../components/UI/Toolbar.svelte';
    import ToolbarGroup from '../components/UI/ToolbarGroup.svelte';
    import ToolbarItem from '../components/UI/ToolbarItem.svelte';

    // General
    let debug = false;

    // Styleguide related
    let styleguide = false;

</script>

<svelte:head>
	<title>Svelte Simple UI</title>
</svelte:head>


<div id="styleguide" class="content">
    <GridLayout>
        <GridItem>
            <Spacer side="top">
                <Toc />
            </Spacer>
        </GridItem>
        <GridItem>

            <h1>Svelte Simple UI</h1>
            <p>An attempt at a simple UI framework with Svelte.</p>


            <div id="components">

                <Component>

                    <h2>Alerts</h2>

                    <h3>Skins</h3>
                    <h4>Default</h4>
                    <Sample>
                        <Alert>I am a default alert.</Alert>
                    </Sample>
                    <h4>Error</h4>
                    <Sample>
                        <Alert type="error">I am an error message.</Alert>
                    </Sample>
                    <h4>Success</h4>
                    <Sample>
                        <Alert type="success">I am a success message.</Alert>
                    </Sample>

                    <h3>Types</h3>
                    <h4>Normal</h4>
                    <Sample>
                        <Alert>Hey, I don't have any options.</Alert>
                    </Sample>
                    <h4>Dismissible</h4>
                    <Sample>
                        <Alert dismissible>Hey, I am dismissible.</Alert>
                    </Sample>
                </Component>


                <Component>
                    <h2>Buttons</h2>
                    <h3>Types</h3>
                    <h4>Icon only</h4>
                    <Sample>
                        <Button icon="close" layout="icon-only">Close</Button>
                    </Sample>
                    <h4>Icon and label</h4>
                    <Sample>
                        <Button icon="close">Close</Button>
                        <Button icon="add">Add</Button>
                        <Button icon="remove">Remove</Button>
                        <Button icon="delete">Delete</Button>
                        <Button icon="question">Help</Button>
                    </Sample>
                </Component>

                <Component>

                    <h2>Inputs</h2>

                    <h3>Text</h3>

                    <Sample>
                        <Input value="Test" />
                    </Sample>

                    <h3>Color</h3>
                    <Sample>
                        <InputColor value="#FF0000" />
                    </Sample>

                </Component>

                <Component>

                    <h2>Box</h2>
                    <Sample>
                        <Box>I am a box.</Box>
                    </Sample>

                </Component>

                <Component>
                    <h2>Blank slate</h2>
                    <Sample>
                        <Blankslate>I am a blank slate. Use me when no content is available.</Blankslate>
                    </Sample>
                </Component>

                <Component>
                    <h2>Panels</h2>
                    <p>Use panels to easily create layouts.</p>
                    <Sample>
                        <Panel>
                            <PanelHeader title="Panel header" />
                            <PanelBody>
                                <p>I am HTML content.</p>
                            </PanelBody>
                        </Panel>
                    </Sample>
                    <Sample>
                        <PanelRow panelCount="2'">
                            <Panel>
                                <PanelHeader title="Panel header" />
                                <PanelBody>
                                    <p>I am HTML content.</p>
                                </PanelBody>
                            </Panel>
                            <Panel>
                                <PanelHeader title="Panel header" />
                                <PanelBody>
                                    <p>I am HTML content.</p>
                                </PanelBody>
                            </Panel>
                        </PanelRow>
                    </Sample>
                    <Sample>
                        <PanelRow>
                            <Panel>
                                <PanelHeader title="Panel header" />
                                <PanelBody>
                                    <p>I am HTML content.</p>
                                </PanelBody>
                            </Panel>
                            <Panel>
                                <PanelHeader title="Panel header" />
                                <PanelBody>
                                    <p>I am HTML content.</p>
                                </PanelBody>
                            </Panel>
                            <Panel>
                                <PanelHeader title="Panel header" />
                                <PanelBody>
                                    <p>I am HTML content.</p>
                                </PanelBody>
                            </Panel>
                        </PanelRow>
                    </Sample>
                </Component>

                <Component>
                    <h2>Form group</h2>
                    <h3>Standard</h3>
                    <Sample>
                        <FormGroupLayout>
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                        </FormGroupLayout>
                    </Sample>

                    <h3>Horizontal</h3>
                    <Sample>
                        <FormGroupLayout type="horizontal">
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                            <FormGroup>
                                <Label>Field name</Label>
                                <Input value="Value" />
                            </FormGroup>
                        </FormGroupLayout>
                    </Sample>
                </Component>

                <Component>

                    <h2>Pickers</h2>

                    <h3>Single option</h3>

                    <Sample>
                        <Select>
                            <option value="value-1">Value 1</option>
                            <option value="value-2">Value 2</option>
                            <option value="value-3">Value 3</option>
                        </Select>
                    </Sample>

                </Component>

                <Component>
                    <h2>Icons</h2>
                    <Sample>
                        <Icon icon="close" />
                        <Icon icon="add" />
                        <Icon icon="remove" />
                        <Icon icon="delete" />
                        <Icon icon="question" />
                    </Sample>
                </Component>

            </div>
        </GridItem>
    </GridLayout>


</div>
