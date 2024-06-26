# GUI常用😭

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

### 布局 （Layout）

- `FlowLayout`布局
    - `FlowLayout()`：创建一个默认的流布局管理器，居中对齐，水平和垂直间距为5个像素。
    - `FlowLayout(int align)`：创建一个指定对齐方式的流布局管理器，对齐方式可以是 `FlowLayout.LEFT`、`FlowLayout.CENTER`、`FlowLayout.RIGHT`。
    - `FlowLayout(int align, int hgap, int vgap)`：创建一个指定对齐方式、水平间距和垂直间距的流布局管理器。

- `BorderLayout`
    - `BorderLayout()`：创建一个默认的边界布局管理器，没有间距。
    - `BorderLayout(int hgap, int vgap)`：创建一个指定水平和垂直间距的边界布局管理器。
    - 组件添加时需要指定位置，如 `add(Component comp, Object constraints)`，其中 `constraints` 可以是 `BorderLayout.NORTH`、`BorderLayout.SOUTH`、`BorderLayout.EAST`、`BorderLayout.WEST`、`BorderLayout.CENTER`。

- `GridLayout`
    - `GridLayout(int rows, int cols)`：创建一个指定行数和列数的网格布局管理器。
    - `GridLayout(int rows, int cols, int hgap, int vgap)`：创建一个指定行数、列数、水平间距和垂直间距的网格布局管理器。
    - 所有单元格大小相同，组件按顺序填充单元格。

- `GridBagLayout`
    - `GridBagLayout()`：创建一个网格包布局管理器，是最灵活的布局管理器，但也最复杂。
    - 需要使用 `GridBagConstraints` 来指定组件的位置、大小、填充方式等。

- `BoxLayout`
    - `BoxLayout(Container target, int axis)`：创建一个箱式布局管理器，可以指定布局的轴向，如 `BoxLayout.X_AXIS`（水平）或 `BoxLayout.Y_AXIS`（垂直）。
    - 组件可以沿着一个轴向排列，可以设置组件之间的间距。

- `CardLayout`
    - `CardLayout()`：创建一个卡片布局管理器，用于管理多个组件，每次只显示一个组件，类似于卡片堆叠。
    - 可以使用 `show(Container parent, String name)` 方法来显示指定的组件。

- `SpringLayout`
    - `SpringLayout()`：创建一个弹簧布局管理器，使用弹簧模型来控制组件的位置和大小。
    - 需要使用 `SpringLayout.Constraints` 来定义组件的约束。

- `GroupLayout`
    - `GroupLayout(Container container)`：创建一个分组布局管理器，用于复杂的布局，通常与 `GroupLayout.DEFAULT_CONSTRAINTS` 一起使用。
    - 可以水平和垂直分组组件，支持自动调整大小和位置。
    - `setBackground(Color bg)`：设置面板的背景颜色。
    - `setBorder(Border border)`：设置面板的边框。
    - `remove(Component comp)`：从面板移除组件。

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