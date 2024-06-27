# `一个简单的GUI程序`

附带了注释了，应该能讲明白

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ExamGUI {
    public static void main(String[] args) {
        JFrame frame = new JFrame("学生考试系统");    //创建底层容器
        frame.setSize(400, 250);

        JPanel panel = new JPanel();    //创建一个面板，方便管理
        frame.add(panel);
        placeComponents(panel); // 自己写的一个函数，用来控制这个面板

        frame.setVisible(true);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);   //创建窗口必备两行代码
    }

    private static void placeComponents(JPanel panel) {
        panel.setLayout(null); //设置为自由布局

        //  流程：1.创建需要的组件 2.设置组件的位置或者其他初始化信息 3.add到容器里

        JLabel questionLabel = new JLabel("问题：Java是由哪个公司开发的？"); //JLabel是一个标签
        questionLabel.setBounds(20, 20, 300, 30);   // 设置在面板里面的位置和大小
        panel.add(questionLabel);

        JRadioButton option1 = new JRadioButton("A. Oracle");
        option1.setBounds(20, 50, 100, 30);
        panel.add(option1);

        JRadioButton option2 = new JRadioButton("B. Microsoft");
        option2.setBounds(20, 80, 100, 30);
        panel.add(option2);

        JRadioButton option3 = new JRadioButton("C. IBM");
        option3.setBounds(20, 110, 100, 30);
        panel.add(option3);

        ButtonGroup group = new ButtonGroup();  // ButtonGroup 是一个不可见的组件，它可以把几个按钮绑定在一起，让它们只能选一个
        group.add(option1);
        group.add(option2);
        group.add(option3);

        JButton submitButton = new JButton("提交");
        submitButton.setBounds(20, 140, 80, 30);
        panel.add(submitButton);

        JLabel resultLabel = new JLabel();
        resultLabel.setBounds(120, 140, 200, 30);
        panel.add(resultLabel);

        submitButton.addActionListener(new ActionListener() {   // 把submitButton注册成为一个监视器，匿名类做监视器，就用再去写一个类了
            @Override                                           // 这一个方法里面要传入的是ActionListener的类或者子类
            public void actionPerformed(ActionEvent e) {        // 所以这里用 `匿名类` 重写了actionPerformed方法``
                if (option1.isSelected()) {                     // .isSelected() 用来查看谁被点击了
                    resultLabel.setText("答案正确！");
                } else {
                    resultLabel.setText("答案错误！");
                }
            }
        });
    }
}
```

运行结果：⬇️
![Snipaste_2024-06-27_10-32-12](https://github.com/Panda-Z-Coding/Panda-Z-Coding.github.io/assets/157597971/ca1d7bf4-d167-4a4e-9cc0-caf6d62159b2)
