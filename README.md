# Personalize-Your-MAUI-DataGrid--Quick-and-Simple-Customization-Techniques

This demo demonstrates quick and simple techniques to personalize the .NET MAUI DataGrid (SfDataGrid) by customizing styles, grouping, and summaries. The sample explains how to:

- Apply visual styles to header, group summary, and cell templates.
- Group rows by a column (for example, `ShipCountry`) and show aggregate summaries for each group.
- Use built-in summary rows and summary columns to display counts and other aggregates.
- Configure grid lines, selection and column mapping to control appearance and behavior.

The `MainPage.xaml` in this repository demonstrates the following practical patterns you can re-use in your app:

- Defining `DataGridTextColumn` entries for explicit column mapping (OrderID, CustomerID, Customer, ShipCity, ShipCountry).
- Enabling `HeaderGridLinesVisibility` and `GridLinesVisibility` for clearer cell boundaries.
- Adding a `GroupColumnDescription` for `ShipCountry` to automatically group rows by country.
- Adding a `DataGridSummaryRow` with a `DataGridSummaryColumn` that computes the number of orders using `CountAggregate` and shows it inline in the group summary row.
- Applying XAML `Style` elements for `DataGridHeaderCell` and `DataGridGroupSummaryCell` to change text attributes, fonts, colors, and background for distinct visual emphasis.

## xaml

The following XAML demonstrates explicit column mappings, grouping, and a group summary row. It follows the same style used in the sample project, so you can copy and paste it into your own page.

```
<syncfusion:SfDataGrid ColumnWidthMode="Auto" SelectionUnit="Row" SelectionMode="Single" NavigationMode="Cell" HeaderGridLinesVisibility="Both" GridLinesVisibility="Both"
						ItemsSource="{Binding OrderInfoCollection}">
	<syncfusion:SfDataGrid.Columns>
		<syncfusion:DataGridTextColumn MappingName="OrderID" HeaderText="Order ID" />
		<syncfusion:DataGridTextColumn MappingName="CustomerID" HeaderText="Customer ID" />
		<syncfusion:DataGridTextColumn MappingName="Customer"  />
		<syncfusion:DataGridTextColumn MappingName="ShipCity"  HeaderText="Ship City" />
		<syncfusion:DataGridTextColumn MappingName="ShipCountry"  HeaderText="Ship Country" />
	</syncfusion:SfDataGrid.Columns>

	<syncfusion:SfDataGrid.GroupColumnDescriptions>
		<syncfusion:GroupColumnDescription ColumnName="ShipCountry"/>
	</syncfusion:SfDataGrid.GroupColumnDescriptions>

	<syncfusion:SfDataGrid.GroupSummaryRows>
		<syncfusion:DataGridSummaryRow ShowSummaryInRow="True" Title="Number of orders : {OrderCount}">
			<syncfusion:DataGridSummaryRow.SummaryColumns>
				<syncfusion:DataGridSummaryColumn Name="OrderCount" Format="{}{Count}" MappingName="OrderID" SummaryType="CountAggregate" />
			</syncfusion:DataGridSummaryRow.SummaryColumns>
		</syncfusion:DataGridSummaryRow>
	</syncfusion:SfDataGrid.GroupSummaryRows>

</syncfusion:SfDataGrid>
```

To learn more about these features, check out the official user guide topics:

- [Grouping in MAUI DataGrid (SfDataGrid)](https://help.syncfusion.com/maui/datagrid/grouping)
- [Summaries in MAUI DataGrid (SfDataGrid)](https://help.syncfusion.com/maui/datagrid/summaries)

##### Conclusion
 
I hope you enjoyed learning about how to personalize your .NET MAUI DataGrid (SfDataGrid).
 
You can refer to our [.NET MAUI DataGrid’s feature tour](https://www.syncfusion.com/maui-controls/maui-datagrid) page to learn about its other groundbreaking feature representations. You can also explore our [.NET MAUI DataGrid Documentation](https://help.syncfusion.com/maui/datagrid/getting-started) to understand how to present and manipulate data. 
For current customers, you can check out our .NET MAUI components on the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/maui) to explore our .NET MAUI DataGrid and other .NET MAUI components.
 
If you have any queries or require clarifications, please let us know in the comments below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [Direct-Trac](https://support.syncfusion.com/create) or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sfdatagrid), or the feedback portal. We are always happy to assist you!
