# Laravel [column types](https://laravel.com/docs/8.x/migrations#available-column-types "Laravel Migrations: Column Types")

The schema builder blueprint offers a variety of methods that correspond to the different types of columns you can add to your database tables. Each of the available methods are listed in the table below:

1. The <span style="font-style:italic; font-weight:bold;">bigIncrements()</span>, <span style="font-style:italic; font-weight:bold;">id()</span>, <span style="font-style:italic; font-weight:bold;">increments()</span> and <span style="font-style:italic; font-weight:bold;">smallIncrements()</span> methods will create an auto-incrementing column with primary key and a not null property having the following particularities:
   * the <span style="font-style:italic; font-weight:bold;">bigIncrements()</span> and <span style="font-style:italic; font-weight:bold;">id()</span> methods are the same and will have <span style="font-style:italic; font-weight:bold;">UNSIGNED</span> attribute and <span style="font-style:italic; font-weight:bold;">BIGINT(20)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">increments()</span> method will have <span style="font-style:italic; font-weight:bold;">UNSIGNED</span> attribute and <span style="font-style:italic; font-weight:bold;">INT(10)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">mediumIncrements()</span> method will have <span style="font-style:italic; font-weight:bold;">UNSIGNED</span> attribute and <span style="font-style:italic; font-weight:bold;">MEDIUMINT(8)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">smallIncrements()</span> method will have <span style="font-style:italic; font-weight:bold;">UNSIGNED</span> attribute and <span style="font-style:italic; font-weight:bold;">SMALLINT(5)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">tinyIncrements()</span> method will have <span style="font-style:italic; font-weight:bold;">UNSIGNED</span> attribute and <span style="font-style:italic; font-weight:bold;">TINYINT(3)</span> type;
   
    <span style="color:red; font-weight:bold;">
        <pre>$table->bigIncrements('columnName');</pre>
        <pre>$table->id();</pre>
        <pre>$table->increments('columnName');</pre>
        <pre>$table->mediumIncrements('columnName');</pre>
        <pre>$table->smallIncrements('columnName');</pre>
        <pre>$table->tinyIncrements('columnName');</pre>
    </span>

2. The <span style="font-style:italic; font-weight:bold;">bigInteger()</span>, <span style="font-style:italic; font-weight:bold;">integer()</span> and <span style="font-style:italic; font-weight:bold;">smallInteger()</span> methods will create an integer column having the following particularities:
   * the <span style="font-style:italic; font-weight:bold;">bigInteger()</span> method will have <span style="font-style:italic; font-weight:bold;">BIGINT(10)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">integer()</span> method will have <span style="font-style:italic; font-weight:bold;">INT(11)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">mediumInteger()</span> method will have <span style="font-style:italic; font-weight:bold;">MEDIUMINT(9)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">smallInteger()</span> method will have <span style="font-style:italic; font-weight:bold;">SMALLINT(6)</span> type;
   * the <span style="font-style:italic; font-weight:bold;">tinyInteger()</span> method will have <span style="font-style:italic; font-weight:bold;">TINYINT(4)</span> type;
   
    <span style="color:red; font-weight:bold;">
        <pre>$table->bigInteger('columnName');</pre>
        <pre>$table->integer('columnName');</pre>
        <pre>$table->mediumInteger('columnName');</pre>
        <pre>$table->smallInteger('columnName');</pre>
        <pre>$table->tinyInteger('columnName');</pre>
    </span>

3. The <span style="font-style:italic; font-weight:bold;">decimal()</span>, <span style="font-style:italic; font-weight:bold;">double()</span> and <span style="font-style:italic; font-weight:bold;">float()</span> methods will create an integer with decimal values column having the following particularities:
   * the <span style="font-style:italic; font-weight:bold;">decimal()</span> method will have <span style="font-style:italic; font-weight:bold;">DECIMAL(8,2)</span> type and 128 bit (28-29 significant digits precision). It's better to use this type when working with applications that require you to store very precise numbers - for instance: financial application, monetary values, financial exchange application etc.;
   * the <span style="font-style:italic; font-weight:bold;">double()</span> method will have <span style="font-style:italic; font-weight:bold;">DOUBLE(8,2)</span> type and 64 bit (15-16 digits precision). It's better to use this type when working with applications that require your to store somehow precise numbers - for instance: statistical applications, marketing analysis etc.;
   * the <span style="font-style:italic; font-weight:bold;">float()</span> method will have <span style="font-style:italic; font-weight:bold;">FLOAT(8,2)</span> type and 32 bit (7 digits precision). It's better to use this type when working with application that do not require you to store very precise numbers - for instance: scientific measurements;
   
    <span style="color:red; font-weight:bold;">
        <pre>$table->decimal('columnName', 8, 2);</pre>
        <pre>$table->double('columnName', 8, 2);</pre>
        <pre>$table->float('columnName', 8, 2);</pre>
    </span>

4. The <span style="font-style:italic; font-weight:bold;">char()</span>, <span style="font-style:italic; font-weight:bold;">longText()</span>, <span style="font-style:italic; font-weight:bold;">mediumText()</span>, <span style="font-style:italic; font-weight:bold;">mediumText()</span>, <span style="font-style:italic; font-weight:bold;">text()</span> and <span style="font-style:italic; font-weight:bold;">string()</span> methods will create a text column having the following particularities:
   * the <span style="font-style:italic; font-weight:bold;">char()</span> method will have <span style="font-style:italic; font-weight:bold;">CHAR()</span> type with a length from 0 to 255. It's better to use this type when working with fixed string values - for instance: dropdown fields;
   * the <span style="font-style:italic; font-weight:bold;">longText()</span>, <span style="font-style:italic; font-weight:bold;">mediumText()</span> and <span style="font-style:italic; font-weight:bold;">text()</span> methods will have <span style="font-style:italic; font-weight:bold;">LONGTEXT</span>, <span style="font-style:italic; font-weight:bold;">MEDIUMTEXT</span> and <span style="font-style:italic; font-weight:bold;">TEXT</span> type with a more than 255 length of string data. It's better to use these types when working with huge amount string values - for instance: description fields;
   * the <span style="font-style:italic; font-weight:bold;">string()</span> method will have <span style="font-style:italic; font-weight:bold;">VARCHAR</span> type with a length from 0 to 255. It's better to use this type when working with variable string values - for instance: email address or address fields etc.;
   
    <span style="color:red; font-weight:bold;">
        <pre>$table->char('columnName', 100);</pre>
        <pre>$table->longText('columnName');</pre>
        <pre>$table->mediumText('columnName');</pre>
        <pre>$table->text('columnName');</pre>
        <pre>$table->string('columnName', 100);</pre>
    </span>