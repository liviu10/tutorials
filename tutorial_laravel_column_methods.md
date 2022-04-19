# Laravel [column types](https://laravel.com/docs/8.x/migrations#available-column-types "Laravel Migrations: Column Types")

The schema builder blueprint offers a variety of methods that correspond to the different types of columns you can add to your database tables. Each of the available methods are listed in the table below:

1. These methods will create auto-incrementing columns with primary key and a not null properties:
   
<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">  (datatype BIGINT(20)):</span> $table->bigIncrements('columnName');
<span style="color:white; font-weight:normal;">     (datatype INT(10)):</span> $table->id();
<span style="color:white; font-weight:normal;">(datatype MEDIUMINT(8)):</span> $table->mediumIncrements('columnName');
<span style="color:white; font-weight:normal;"> (datatype SMALLINT(5)):</span> $table->smallIncrements('columnName');
<span style="color:white; font-weight:normal;">  (datatype TINYINT(5)):</span> $table->tinyIncrements('columnName');</pre>
</span>

2. These methods will create integer columns:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">  (datatype BIGINT(20)):</span> $table->bigInteger('columnName');
<span style="color:white; font-weight:normal;">     (datatype INT(10)):</span> $table->integer();
<span style="color:white; font-weight:normal;">(datatype MEDIUMINT(8)):</span> $table->mediumInteger('columnName');
<span style="color:white; font-weight:normal;"> (datatype SMALLINT(5)):</span> $table->smallInteger('columnName');
<span style="color:white; font-weight:normal;">  (datatype TINYINT(5)):</span> $table->tinyInteger('columnName');</pre>
</span>

3. These methods will create integer with decimal values columns.

   * the <span style="font-style:italic; font-weight:bold;">decimal()</span> method will have <span style="font-style:italic; font-weight:bold;">DECIMAL(8,2)</span> type and 128 bit (28-29 significant digits precision). It's better to use this type when working with applications that require you to store very precise numbers - for instance: financial application, monetary values, financial exchange application etc.;
   * the <span style="font-style:italic; font-weight:bold;">double()</span> method will have <span style="font-style:italic; font-weight:bold;">DOUBLE(8,2)</span> type and 64 bit (15-16 digits precision). It's better to use this type when working with applications that require your to store somehow precise numbers - for instance: statistical applications, marketing analysis etc.;
   * the <span style="font-style:italic; font-weight:bold;">float()</span> method will have <span style="font-style:italic; font-weight:bold;">FLOAT(8,2)</span> type and 32 bit (7 digits precision). It's better to use this type when working with application that do not require you to store very precise numbers - for instance: scientific measurements;

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">(datatype DECIMAL(8,2)):</span> $table->decimal('columnName', 8, 2);
<span style="color:white; font-weight:normal;"> (datatype DOUBLE(8,2)):</span> $table->double('columnName', 8, 2);
<span style="color:white; font-weight:normal;">  (datatype FLOAT(8,2)):</span> $table->float('columnName', 8, 2);</pre>
</span>

4. These methods will create text columns.

   * the <span style="font-style:italic; font-weight:bold;">char()</span> method will have <span style="font-style:italic; font-weight:bold;">CHAR()</span> type with a length from 0 to 255. It's better to use this type when working with fixed string values - for instance: dropdown fields;
   * the <span style="font-style:italic; font-weight:bold;">longText()</span>, <span style="font-style:italic; font-weight:bold;">mediumText()</span> and <span style="font-style:italic; font-weight:bold;">text()</span> methods will have <span style="font-style:italic; font-weight:bold;">LONGTEXT</span>, <span style="font-style:italic; font-weight:bold;">MEDIUMTEXT</span> and <span style="font-style:italic; font-weight:bold;">TEXT</span> type with a more than 255 length of string data. It's better to use these types when working with huge amount string values - for instance: description fields;
   * the <span style="font-style:italic; font-weight:bold;">string()</span> method will have <span style="font-style:italic; font-weight:bold;">VARCHAR</span> type with a length from 0 to 255. It's better to use this type when working with variable string values - for instance: email address or address fields etc.;

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">      (datatype CHAR()):</span> $table->char('columnName', 100);
<span style="color:white; font-weight:normal;">  (datatype LONGTEXT()):</span> $table->longText('columnName');
<span style="color:white; font-weight:normal;">(datatype MEDIUMTEXT()):</span> $table->mediumText('columnName');
<span style="color:white; font-weight:normal;">      (datatype TEXT()):</span> $table->text('columnName');
<span style="color:white; font-weight:normal;">   (datatype VARCHAR()):</span> $table->string('columnName', 100);</pre>
</span>
