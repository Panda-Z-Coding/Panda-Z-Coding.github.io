# **`GUI常用😭`**

### 容器（Containers）

#### JFrame
- `setTitle(String title)`：设置窗口标题。
- `setSize(int width, int height)`：设置窗口大小。
- `setLocation(int x, int y)`：设置窗口在屏幕上的位置。
- `setDefaultCloseOperation(int operation)`：设置关闭窗口时的默认操作，例如 `JFrame.EXIT_ON_CLOSE`。
- `setVisible(boolean b)`：设置窗口是否可见。
- `getContentPane().add(Component comp)`：向窗口添加组件。
- `setResizable(boolean resizable)`：设置窗口是否可以调整大小。

#### JPanel
- `add(Component comp)`：向面板添加组件。
- `setLayout(LayoutManager manager)`：设置面板的布局管理器。
- `setBackground(Color bg)`：设置面板的背景颜色。
- `setBorder(Border border)`：设置面板的边框。
- `remove(Component comp)`：从面板移除组件。

#### JTabbedPane
- `addTab(String title, Component component)`：向选项卡窗格添加一个带有标题的组件。
- `setTabPlacement(int placement)`：设置选项卡的位置（顶部、底部、左侧、右侧）。
- `setSelectedIndex(int index)`：设置当前选中的选项卡索引。
- `setTabComponentAt(int index, Component comp)`：在指定索引位置设置选项卡组件。

### 组件（Components）

#### JButton
- `addActionListener(ActionListener listener)`：添加动作事件监听器。
- `setText(String text)`：设置按钮上的文本。
- `setIcon(Icon icon)`：设置按钮上的图标。
- `setEnabled(boolean b)`：设置按钮是否可用。

#### JTextField
- `setText(String text)`：设置文本框中的文本。
- `getText()`：获取文本框中的文本。
- `setEditable(boolean b)`：设置文本框是否可编辑。
- `setColumns(int columns)`：设置文本框的列数。

#### JCheckBox
- `addActionListener(ActionListener listener)`：添加动作事件监听器。
- `setSelected(boolean selected)`：设置复选框是否被选中。
- `setText(String text)`：设置复选框旁边的文本。

#### JRadioButton
- `addActionListener(ActionListener listener)`：添加动作事件监听器。
- `setSelected(boolean selected)`：设置单选按钮是否被选中。
- `setText(String text)`：设置单选按钮旁边的文本。
- `setIcon(Icon icon)`：设置单选按钮的图标。

#### JComboBox
- `addItem(Object anItem)`：向组合框添加项目。
- `setSelectedItem(Object anItem)`：设置组合框中选中的项目。
- `addActionListener(ActionListener listener)`：添加动作事件监听器。
- `setEditable(boolean b)`：设置组合框是否可编辑。

### 监听器（Listeners）

#### ActionListener
- `actionPerformed(ActionEvent e)`：当动作事件发生时调用。通常用于按钮点击、菜单选择等。

#### ItemListener
- `itemStateChanged(ItemEvent e)`：当项目状态改变时调用。通常用于复选框、单选按钮的状态变化。

#### DocumentListener
- `insertUpdate(DocumentEvent e)`：当文档被插入时调用。
- `removeUpdate(DocumentEvent e)`：当文档被移除时调用。
- `changedUpdate(DocumentEvent e)`：当文档的属性改变时调用。通常用于文本框的文本变化。

#### MouseListener
- `mouseClicked(MouseEvent e)`：当鼠标点击时调用。
- `mousePressed(MouseEvent e)`：当鼠标按下时调用。
- `mouseReleased(MouseEvent e)`：当鼠标释放时调用。
- `mouseEntered(MouseEvent e)`：当鼠标进入组件时调用。
- `mouseExited(MouseEvent e)`：当鼠标离开组件时调用。

#### KeyListener
- `keyPressed(KeyEvent e)`：当键盘按键被按下时调用。
- `keyReleased(KeyEvent e)`：当键盘按键被释放时调用。
- `keyTyped(KeyEvent e)`：当键盘按键被敲击时调用。

这些方法和监听器是Java Swing编程中的基础，通过它们可以创建复杂的用户界面和响应用户交互。每个组件和监听器都有其特定的API文档，可以在需要时查阅以获取更详细的信息。