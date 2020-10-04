# android-pie-chart-using-mpandroidchart

## build.gradle

    repositories  {
        maven { url 'https://jitpack.io' }
    }

## app/build.gradle

    implementation 'com.github.PhilJay:MPAndroidChart:v3.1.0-alpha'

## MainActivity.java

```java
public void onClickChange(View view) {
    PieChart pie_chart = (PieChart)findViewById(R.id.pie_chart);
    pie_chart.setTouchEnabled(false);
    pie_chart.getLegend().setEnabled(false);
    pie_chart.getDescription().setText("");
    List entries = new ArrayList<>();
    entries.add(new PieEntry(1.0f));
    entries.add(new PieEntry(1.0f));
    entries.add(new PieEntry(1.0f));
    PieDataSet set = new PieDataSet(entries, "R");
    set.setColors(Color.parseColor("#FF0000"), Color.parseColor("#00FF00"), Color.parseColor("#0000FF"));
    PieData data = new PieData(set);
    pie_chart.setData(data);
    pie_chart.invalidate();
}
```

## activity_mail.xml
```xml
<?xml version="1.0" encoding="utf-8" ?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
              xmlns:tools="http://schemas.android.com/tools"
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:padding="16dp"
              android:orientation="vertical"
              tools:context=".MainActivity">
    <Button android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:onClick="onClickChange" />

    <com.github.mikephil.charting.charts.PieChart android:id="@+id/pie_chart"
                                                  android:layout_width="match_parent"
                                                  android:layout_height="match_parent" />

</LinearLayout>
```
