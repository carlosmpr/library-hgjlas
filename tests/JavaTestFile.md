---
  title: 'JavaTestFile.java'
  description: 'component description'
  pubDate: 'July 30, 2024'
  author: 'Carlos Polanco'
  ---
  
  
  
  # JavaTestFile.java
  # BMI Chart Explanation

The provided code is a Java program that generates a BMI (Body Mass Index) trend chart using the JFreeChart library. Below is a breakdown of the code:

### Libraries Used
- **JFreeChart**: A popular Java library for creating a variety of charts including pie charts, bar charts, line charts, etc.
- **Swing**: Java's GUI toolkit for creating graphical user interfaces.

### Class: BMIChart
- **Extends ApplicationFrame**: The `BMIChart` class extends `ApplicationFrame`, which is a Swing container that represents the main window of the application.

### Constructor: BMIChart(String title)
- **Parameters**: `title` - The title of the BMI chart.
- **Operation**: Initializes the BMIChart with the provided title, creates a JFreeChart using the `createChart` method with the dataset created by `createDataset`, and sets up the chart panel to display the chart.
- **Usage**: `BMIChart example = new BMIChart("BMI Trend Chart");`

### Method: createDataset()
- **Return Type**: XYSeriesCollection
- **Operation**: Creates a dataset containing two XYSeries (Person 1 and Person 2) with BMI values at different time points.
- **Usage**: Called internally to generate the dataset for the BMI chart.

### Method: createChart(XYSeriesCollection dataset)
- **Parameters**: `dataset` - XYSeriesCollection containing the data points for the chart.
- **Return Type**: JFreeChart
- **Operation**: Creates an XYLineChart with the provided dataset, sets chart properties like title, axes labels, and orientation, and customizes the plot renderer.
- **Usage**: Internally called to create the BMI trend chart.

### Method: main(String[] args)
- **Operation**: Entry point of the program. It creates an instance of BMIChart, sets its size, location, default close operation, and makes the chart visible.
- **Usage**: Executes the BMIChart application.

### Example Usage
```java
public static void main(String[] args) {
    SwingUtilities.invokeLater(() -> {
        BMIChart example = new BMIChart("BMI Trend Chart");
        example.setSize(800, 600);
        example.setLocationRelativeTo(null);
        example.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        example.setVisible(true);
    });
}
```

This code snippet creates a BMI trend chart application with the title "BMI Trend Chart" and displays it on the screen with a size of 800x600 pixels.

Overall, the code demonstrates how to use JFreeChart to create a simple BMI trend chart with two data series representing different individuals' BMI values over time.
  
  ## Component Code
  ```jsx
  import org.jfree.chart.ChartFactory;
import org.jfree.chart.ChartPanel;
import org.jfree.chart.JFreeChart;
import org.jfree.chart.plot.PlotOrientation;
import org.jfree.chart.plot.XYPlot;
import org.jfree.chart.renderer.xy.XYLineAndShapeRenderer;
import org.jfree.data.xy.XYSeries;
import org.jfree.data.xy.XYSeriesCollection;
import org.jfree.ui.ApplicationFrame;

import javax.swing.*;
import java.awt.*;

public class BMIChart extends ApplicationFrame {

    public BMIChart(String title) {
        super(title);
        JFreeChart xylineChart = createChart(createDataset());
        ChartPanel chartPanel = new ChartPanel(xylineChart);
        chartPanel.setPreferredSize(new Dimension(800, 600));
        setContentPane(chartPanel);
    }

    private XYSeriesCollection createDataset() {
        XYSeries series1 = new XYSeries("Person 1");
        series1.add(1, 22.5);
        series1.add(2, 23.0);
        series1.add(3, 22.8);
        series1.add(4, 23.5);

        XYSeries series2 = new XYSeries("Person 2");
        series2.add(1, 25.0);
        series2.add(2, 25.4);
        series2.add(3, 25.1);
        series2.add(4, 26.0);

        XYSeriesCollection dataset = new XYSeriesCollection();
        dataset.addSeries(series1);
        dataset.addSeries(series2);

        return dataset;
    }

    private JFreeChart createChart(XYSeriesCollection dataset) {
        JFreeChart chart = ChartFactory.createXYLineChart(
                "BMI Trends",
                "Time (Months)",
                "BMI",
                dataset,
                PlotOrientation.VERTICAL,
                true, true, false);

        XYPlot plot = chart.getXYPlot();
        XYLineAndShapeRenderer renderer = new XYLineAndShapeRenderer();
        plot.setRenderer(renderer);
        return chart;
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            BMIChart example = new BMIChart("BMI Trend Chart");
            example.setSize(800, 600);
            example.setLocationRelativeTo(null);
            example.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
            example.setVisible(true);
        });
    }
}
  ```
  