# Hadoop Book Example Code

This repository contains the example code for [Hadoop: The Definitive Guide, Fourth Edition](http://shop.oreilly.com/product/0636920033448.do)
by Tom White (O'Reilly, 2014).

Code for the [First], [Second], and [Third] Editions is also available.

Note that the chapter names and numbering has changed between editions, see
[Chapter Numbers By Edition](https://github.com/tomwhite/hadoop-book/wiki/Chapter-Numbers-By-Edition).

[First]: http://github.com/tomwhite/hadoop-book/tree/1e
[Second]: http://github.com/tomwhite/hadoop-book/tree/2e
[Third]: http://github.com/tomwhite/hadoop-book/tree/3e

## Building and Running

To build the code, you will first need to have installed Maven and Java. Then type

```bash
% mvn package -DskipTests
```

This will do a full build and create example JAR files in the top-level directory (e.g. 
`hadoop-examples.jar`).

To run the examples from a particular chapter, first install the component 
needed for the chapter (e.g. Hadoop, Pig, Hive, etc), then run the command lines shown 
in the chapter.

Sample datasets are provided in the [input](input) directory, but the full weather dataset
is not contained there due to size restrictions. You can find information about how to obtain 
the full weather dataset on the book's website at [http://www.hadoopbook.com/]
(http://www.hadoopbook.com/).

## Hadoop Component Versions

This edition of the book works with Hadoop 2. It has not been tested extensively with 
Hadoop 1, although most of it should work.

For the precise versions of each component that the code has been tested with, see 
[book/pom.xml](book/pom.xml).

## Copyright

Copyright (C) 2014 Tom White





```js
.
├── README.md
├── appc
│   └── src
│       └── main
│           └── sh
│               ├── create_ncdc_files.sh
│               ├── load_ncdc.sh
│               ├── load_ncdc_map.sh
│               └── ncdc_files.txt
├── book
│   ├── pom.xml
│   └── src
│       └── main
│           └── assembly
│               ├── jar.xml
│               └── oozie-workflow-application.xml
├── ch02-mr-intro
│   ├── pom.xml
│   └── src
│       └── main
│           ├── awk
│           │   └── max_temperature.sh
│           ├── cpp
│           │   ├── Makefile
│           │   └── max_temperature.cpp
│           ├── examples
│           │   ├── MaxTemperature
│           │   │   ├── input.txt
│           │   │   └── output
│           │   │       └── part-r-00000
│           │   ├── MaxTemperatureWithCombiner
│           │   │   ├── input.txt
│           │   │   └── output
│           │   │       └── part-r-00000
│           │   ├── OldMaxTemperature
│           │   │   ├── input.txt
│           │   │   └── output
│           │   │       └── part-00000
│           │   ├── max_temperature.cpp.input.txt
│           │   ├── max_temperature_hadoop.input.txt
│           │   ├── max_temperature_hadoop_cluster.input.txt
│           │   └── max_temperature_py
│           │       ├── 2
│           │       │   ├── input.txt
│           │       │   └── output
│           │       │       └── part-00000
│           │       ├── input.txt
│           │       ├── output
│           │       │   └── part-r-00000
│           │       └── pseudo
│           │           ├── input.txt
│           │           └── output
│           │               └── part-00000
│           ├── java
│           │   ├── MaxTemperature.java
│           │   ├── MaxTemperatureMapper.java
│           │   ├── MaxTemperatureReducer.java
│           │   ├── MaxTemperatureWithCombiner.java
│           │   ├── OldMaxTemperature.java
│           │   └── oldapi
│           │       ├── MaxTemperature.java
│           │       ├── MaxTemperatureMapper.java
│           │       ├── MaxTemperatureReducer.java
│           │       └── MaxTemperatureWithCombiner.java
│           ├── python
│           │   ├── max_temperature_map.py
│           │   └── max_temperature_reduce.py
│           ├── ruby
│           │   ├── max_temperature_map.rb
│           │   └── max_temperature_reduce.rb
│           └── sh
│               └── max_temp.sh
├── ch03-hdfs
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── conf
│       │   │   ├── core-site.xml
│       │   │   └── hdfs-site.xml
│       │   ├── java
│       │   │   ├── DateRangePathFilter.java
│       │   │   ├── FileCopyWithProgress.java
│       │   │   ├── FileSystemCat.java
│       │   │   ├── FileSystemDoubleCat.java
│       │   │   ├── ListStatus.java
│       │   │   ├── RegexExcludePathFilter.java
│       │   │   ├── RegexPathFilter.java
│       │   │   └── URLCat.java
│       │   └── sh
│       │       ├── file.sh
│       │       └── hars.sh
│       └── test
│           └── java
│               ├── CoherencyModelTest.java
│               ├── FileSystemDeleteTest.java
│               ├── FileSystemGlobTest.java
│               └── ShowFileStatusTest.java
├── ch04-yarn
│   ├── capacity-scheduler.xml
│   └── fair-scheduler.xml
├── ch05-io
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── examples
│       │   │   ├── FileDecompressor.java.input.txt
│       │   │   ├── MapFile-data-head.input.txt
│       │   │   ├── MapFile-data-head.output.txt
│       │   │   ├── MapFile-index.input.txt
│       │   │   ├── MapFile-index.output.txt
│       │   │   ├── MapFile-ls.input.txt
│       │   │   ├── MapFile-ls.output.txt
│       │   │   ├── MapFileWriteDemo.java.input.txt
│       │   │   ├── MaxTemperatureWithCompression
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000.gz
│       │   │   ├── MaxTemperatureWithMapOutputCompression.ignore
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   ├── SequenceFileMapReduceSort.java.input.txt
│       │   │   ├── SequenceFileMapReduceSortResults.java.input.txt
│       │   │   ├── SequenceFileMapReduceSortResults.java.output.txt
│       │   │   ├── SequenceFileMapReduceSortResults.java.pre.sh
│       │   │   ├── SequenceFileReadDemo.java.input.txt
│       │   │   ├── SequenceFileReadDemo.java.output.txt
│       │   │   ├── SequenceFileReadDemo.java.pre.sh
│       │   │   ├── SequenceFileToMapFileConverter-fix.java.input.txt
│       │   │   ├── SequenceFileToMapFileConverter-mv.java.input.txt
│       │   │   ├── SequenceFileToMapFileConverter-sort.java.input.txt
│       │   │   ├── SequenceFileWriteDemo.java.input.txt
│       │   │   ├── SequenceFileWriteDemo.java.output.txt
│       │   │   ├── StreamCompressor.java.input.txt
│       │   │   ├── StreamCompressor.java.output.txt
│       │   │   ├── TextIterator.java.input.txt
│       │   │   ├── TextIterator.java.output.txt
│       │   │   ├── hadoop-fs-text.input.txt
│       │   │   └── hadoop-fs-text.output.txt
│       │   └── java
│       │       ├── FileDecompressor.java
│       │       ├── IntPair.java
│       │       ├── MapFileFixer.java
│       │       ├── MapFileWriteDemo.java
│       │       ├── MaxTemperatureWithCompression.java
│       │       ├── MaxTemperatureWithMapOutputCompression.java
│       │       ├── PooledStreamCompressor.java
│       │       ├── SequenceFileReadDemo.java
│       │       ├── SequenceFileWriteDemo.java
│       │       ├── StreamCompressor.java
│       │       ├── TextArrayWritable.java
│       │       ├── TextIterator.java
│       │       ├── TextPair.java
│       │       └── oldapi
│       │           ├── IntPair.java
│       │           ├── MaxTemperatureWithCompression.java
│       │           ├── MaxTemperatureWithMapOutputCompression.java
│       │           └── TextPair.java
│       └── test
│           ├── java
│           │   ├── ArrayWritableTest.java
│           │   ├── BinaryOrTextWritable.java
│           │   ├── BooleanWritableTest.java
│           │   ├── BytesWritableTest.java
│           │   ├── FileDecompressorTest.java
│           │   ├── GenericWritableTest.java
│           │   ├── IntPairTest.java
│           │   ├── IntWritableTest.java
│           │   ├── MapFileSeekTest.java
│           │   ├── MapWritableTest.java
│           │   ├── NullWritableTest.java
│           │   ├── ObjectWritableTest.java
│           │   ├── SequenceFileSeekAndSyncTest.java
│           │   ├── StringTextComparisonTest.java
│           │   ├── TextPairTest.java
│           │   ├── TextTest.java
│           │   ├── VIntWritableTest.java
│           │   ├── VLongWritableTest.java
│           │   └── WritableTestBase.java
│           └── resources
│               └── file.gz
├── ch06-mr-dev
│   ├── input
│   │   └── ncdc
│   │       └── micro
│   │           └── sample.txt
│   ├── output
│   │   ├── _SUCCESS
│   │   └── part-r-00000
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── examples
│       │   │   ├── ConfigurationPrinterSystem.java.input.txt
│       │   │   ├── ConfigurationPrinterWithConf.java.input.txt
│       │   │   ├── ConfigurationPrinterWithConf.java.output.txt
│       │   │   ├── ConfigurationPrinterWithConfAndD.java.input.txt
│       │   │   ├── ConfigurationPrinterWithD.java.input.txt
│       │   │   ├── ConfigurationPrinterWithD.java.output.txt
│       │   │   ├── MaxTemperatureDriver.java.input.txt
│       │   │   ├── MaxTemperatureDriverV2.ignore
│       │   │   │   └── input.txt
│       │   │   ├── MaxTemperatureDriverV2GOP.ignore
│       │   │   │   └── input.txt
│       │   │   ├── MaxTemperatureDriverV3
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   └── MaxTemperatureDriverV3GOP
│       │   │       ├── input.txt
│       │   │       └── output
│       │   │           └── part-r-00000
│       │   ├── java
│       │   │   ├── ConfigurationPrinter.java
│       │   │   ├── LoggingDriver.java
│       │   │   ├── LoggingIdentityMapper.java
│       │   │   ├── v1
│       │   │   │   ├── MaxTemperatureMapper.java
│       │   │   │   └── MaxTemperatureReducer.java
│       │   │   ├── v2
│       │   │   │   ├── MaxTemperatureDriver.java
│       │   │   │   ├── MaxTemperatureMapper.java
│       │   │   │   └── NcdcRecordParser.java
│       │   │   ├── v3
│       │   │   │   ├── MaxTemperatureDriver.java
│       │   │   │   └── MaxTemperatureMapper.java
│       │   │   └── v4
│       │   │       ├── MaxTemperatureDriver.java
│       │   │       ├── MaxTemperatureMapper.java
│       │   │       └── NcdcRecordParser.java
│       │   └── resources
│       │       ├── configuration-1.xml
│       │       ├── configuration-2.xml
│       │       ├── max-temp-workflow
│       │       │   └── workflow.xml
│       │       └── max-temp-workflow.properties
│       └── test
│           ├── java
│           │   ├── MultipleResourceConfigurationTest.java
│           │   ├── SingleResourceConfigurationTest.java
│           │   ├── v1
│           │   │   ├── MaxTemperatureMapperTest.java
│           │   │   └── MaxTemperatureReducerTest.java
│           │   ├── v2
│           │   │   ├── MaxTemperatureDriverMiniTest.java
│           │   │   ├── MaxTemperatureDriverTest.java
│           │   │   └── MaxTemperatureMapperTest.java
│           │   └── v4
│           │       └── MaxTemperatureMapperTest.java
│           └── resources
│               └── expected.txt
├── ch08-mr-types
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── examples
│       │   │   ├── MaxTemperatureWithMultipleInputs
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   ├── MinimalMapReduce
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-00000
│       │   │   ├── MinimalMapReduce.java.input.txt
│       │   │   ├── MinimalMapReduceWithDefaults
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-00000
│       │   │   ├── PartitionByStationUsingMultipleOutputFormat.java.input.txt
│       │   │   ├── PartitionByStationUsingMultipleOutputs
│       │   │   │   ├── 2
│       │   │   │   │   ├── input.txt
│       │   │   │   │   └── output
│       │   │   │   │       ├── 029070-99999-r-00000
│       │   │   │   │       ├── 029500-99999-r-00000
│       │   │   │   │       ├── 029600-99999-r-00000
│       │   │   │   │       ├── 029720-99999-r-00000
│       │   │   │   │       ├── 029810-99999-r-00000
│       │   │   │   │       ├── 227070-99999-r-00000
│       │   │   │   │       └── part-r-00000
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       ├── 029070-99999-r-00000
│       │   │   │       ├── 029500-99999-r-00000
│       │   │   │       ├── 029600-99999-r-00000
│       │   │   │       ├── 029720-99999-r-00000
│       │   │   │       ├── 029810-99999-r-00000
│       │   │   │       ├── 227070-99999-r-00000
│       │   │   │       └── part-r-00000
│       │   │   ├── PartitionByStationYearUsingMultipleOutputs
│       │   │   │   ├── 2
│       │   │   │   │   ├── input.txt
│       │   │   │   │   └── output
│       │   │   │   │       ├── 029070-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       ├── 029500-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       ├── 029600-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       ├── 029720-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       ├── 029810-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       ├── 227070-99999
│       │   │   │   │       │   ├── 1901
│       │   │   │   │       │   │   └── part-r-00000
│       │   │   │   │       │   └── 1902
│       │   │   │   │       │       └── part-r-00000
│       │   │   │   │       └── part-r-00000
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       ├── 029070-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       ├── 029500-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       ├── 029600-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       ├── 029720-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       ├── 029810-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       ├── 227070-99999
│       │   │   │       │   ├── 1901
│       │   │   │       │   │   └── part-r-00000
│       │   │   │       │   └── 1902
│       │   │   │       │       └── part-r-00000
│       │   │   │       └── part-r-00000
│       │   │   ├── SmallFilesToSequenceFileConverter.ignore
│       │   │   │   └── input.txt
│       │   │   ├── SmallFilesToSequenceFileConverter.java.input.txt
│       │   │   ├── default_streaming.input.txt
│       │   │   └── minimal_streaming.input.txt
│       │   ├── java
│       │   │   ├── MaxTemperatureWithMultipleInputs.java
│       │   │   ├── MinimalMapReduce.java
│       │   │   ├── MinimalMapReduceWithDefaults.java
│       │   │   ├── NonSplittableTextInputFormat.java
│       │   │   ├── PartitionByStationUsingMultipleOutputs.java
│       │   │   ├── PartitionByStationYearUsingMultipleOutputs.java
│       │   │   ├── SmallFilesToSequenceFileConverter.java
│       │   │   ├── StationPartitioner.java
│       │   │   ├── WholeFileInputFormat.java
│       │   │   ├── WholeFileRecordReader.java
│       │   │   └── oldapi
│       │   │       ├── MaxTemperatureWithMultipleInputs.java
│       │   │       ├── MinimalMapReduce.java
│       │   │       ├── MinimalMapReduceWithDefaults.java
│       │   │       ├── NonSplittableTextInputFormat.java
│       │   │       ├── PartitionByStationUsingMultipleOutputFormat.java
│       │   │       ├── PartitionByStationUsingMultipleOutputs.java
│       │   │       ├── PartitionByStationYearUsingMultipleOutputFormat.java
│       │   │       ├── SmallFilesToSequenceFileConverter.java
│       │   │       ├── StationPartitioner.java
│       │   │       ├── WholeFileInputFormat.java
│       │   │       └── WholeFileRecordReader.java
│       │   └── sh
│       │       └── streaming.sh
│       └── test
│           └── java
│               └── TextInputFormatsTest.java
├── ch09-mr-features
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── examples
│       │   │   ├── JoinRecordWithStationName
│       │   │   │   ├── 2
│       │   │   │   │   ├── input.txt
│       │   │   │   │   └── output
│       │   │   │   │       └── part-r-00000
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   ├── LookupRecordByTemperature.java.input.txt
│       │   │   ├── LookupRecordByTemperature.java.output.txt
│       │   │   ├── LookupRecordsByTemperature.java.input.txt
│       │   │   ├── LookupRecordsByTemperature.java.output.txt
│       │   │   ├── MaxTemperatureByStationNameUsingDistributedCacheFile.java.input.txt
│       │   │   ├── MaxTemperatureByStationNameUsingDistributedCacheFileApi.ignore
│       │   │   │   └── input.txt
│       │   │   ├── MaxTemperatureUsingSecondarySort
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   ├── MaxTemperatureWithCounters
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       └── part-r-00000
│       │   │   ├── MaxTemperatureWithCounters.java.input.txt
│       │   │   ├── MissingTemperatureFields.java.input.txt
│       │   │   ├── SortByTemperatureToMapFile.ignore
│       │   │   │   └── input.txt
│       │   │   ├── SortByTemperatureUsingHashPartitioner.ignore
│       │   │   │   └── input.txt
│       │   │   ├── SortByTemperatureUsingHashPartitioner.java.input.txt
│       │   │   ├── SortByTemperatureUsingTotalOrderPartitioner.java.input.txt
│       │   │   ├── SortDataPreprocessor.ignore
│       │   │   │   └── input.txt
│       │   │   └── SortDataPreprocessor.java.input.txt
│       │   ├── java
│       │   │   ├── JoinRecordMapper.java
│       │   │   ├── JoinRecordWithStationName.java
│       │   │   ├── JoinReducer.java
│       │   │   ├── JoinStationMapper.java
│       │   │   ├── LookupRecordByTemperature.java
│       │   │   ├── LookupRecordsByTemperature.java
│       │   │   ├── MaxTemperatureByStationNameUsingDistributedCacheFile.java
│       │   │   ├── MaxTemperatureUsingSecondarySort.java
│       │   │   ├── MaxTemperatureWithCounters.java
│       │   │   ├── MissingTemperatureFields.java
│       │   │   ├── SortByTemperatureToMapFile.java
│       │   │   ├── SortByTemperatureUsingHashPartitioner.java
│       │   │   ├── SortByTemperatureUsingTotalOrderPartitioner.java
│       │   │   ├── SortDataPreprocessor.java
│       │   │   ├── TemperatureDistribution.java
│       │   │   └── oldapi
│       │   │       ├── JoinRecordMapper.java
│       │   │       ├── JoinRecordWithStationName.java
│       │   │       ├── JoinReducer.java
│       │   │       ├── JoinStationMapper.java
│       │   │       ├── LookupRecordByTemperature.java
│       │   │       ├── LookupRecordsByTemperature.java
│       │   │       ├── MaxTemperatureByStationNameUsingDistributedCacheFile.java
│       │   │       ├── MaxTemperatureByStationNameUsingDistributedCacheFileApi.java
│       │   │       ├── MaxTemperatureUsingSecondarySort.java
│       │   │       ├── MaxTemperatureWithCounters.java
│       │   │       ├── MissingTemperatureFields.java
│       │   │       ├── SortByTemperatureToMapFile.java
│       │   │       ├── SortByTemperatureUsingHashPartitioner.java
│       │   │       ├── SortByTemperatureUsingTotalOrderPartitioner.java
│       │   │       ├── SortDataPreprocessor.java
│       │   │       └── TemperatureDistribution.java
│       │   ├── python
│       │   │   ├── max_daily_temp_map.py
│       │   │   ├── max_daily_temp_reduce.py
│       │   │   ├── mean_max_daily_temp.sh
│       │   │   ├── mean_max_daily_temp_map.py
│       │   │   ├── mean_max_daily_temp_reduce.py
│       │   │   ├── secondary_sort.sh
│       │   │   ├── secondary_sort_map.py
│       │   │   └── secondary_sort_reduce.py
│       │   ├── r
│       │   │   ├── fixed-partitions
│       │   │   ├── output
│       │   │   ├── output_sorted
│       │   │   ├── sampled-partitions
│       │   │   ├── temperature_distribution.png
│       │   │   └── temperature_distribution.r
│       │   └── resources
│       │       ├── MaxTemperatureWithCounters_Temperature.properties
│       │       └── oldapi
│       │           └── MaxTemperatureWithCounters_Temperature.properties
│       └── test
│           └── java
│               └── KeyFieldBasedComparatorTest.java
├── ch10-setup
│   └── src
│       └── main
│           ├── conf
│           │   ├── core-site.xml
│           │   ├── hdfs-site.xml
│           │   └── yarn-site.xml
│           └── sh
│               └── trash.sh
├── ch12-avro
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── assembly
│       │   │   └── job.xml
│       │   ├── c
│       │   │   └── dump_pairs.c
│       │   ├── examples
│       │   │   ├── AvroGenericMaxTemperature
│       │   │   │   ├── input.txt
│       │   │   │   └── output
│       │   │   │       ├── _SUCCESS
│       │   │   │       └── part-r-00000.avro
│       │   │   └── AvroSort
│       │   │       ├── input.txt
│       │   │       └── output
│       │   │           ├── _SUCCESS
│       │   │           └── part-r-00000.avro
│       │   ├── java
│       │   │   ├── AvroGenericMaxTemperature.java
│       │   │   ├── AvroSort.java
│       │   │   ├── NcdcRecordParser.java
│       │   │   └── oldapi
│       │   │       ├── AvroGenericMaxTemperature.java
│       │   │       ├── AvroProjection.java
│       │   │       ├── AvroSort.java
│       │   │       ├── AvroSpecificMaxTemperature.java
│       │   │       └── NcdcRecordParser.java
│       │   ├── py
│       │   │   ├── test_avro.py
│       │   │   └── write_pairs.py
│       │   └── resources
│       │       ├── AliasedStringPair.avsc
│       │       ├── Array.avsc
│       │       ├── Enum.avsc
│       │       ├── Fixed.avsc
│       │       ├── Map.avsc
│       │       ├── NewStringPair.avsc
│       │       ├── NewStringPairWithNull.avsc
│       │       ├── ProjectedStringPair.avsc
│       │       ├── SortedStringPair.avsc
│       │       ├── StringPair.avsc
│       │       ├── SwitchedStringPair.avsc
│       │       ├── Union.avsc
│       │       └── WeatherRecord.avsc
│       └── test
│           └── java
│               └── AvroTest.java
├── ch13-parquet
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── assembly
│       │   │   └── job.xml
│       │   ├── examples
│       │   │   └── TextToParquetWithAvro
│       │   │       ├── input.txt
│       │   │       └── output
│       │   │           ├── _SUCCESS
│       │   │           ├── _metadata
│       │   │           └── part-m-00000.parquet
│       │   └── java
│       │       ├── ParquetToTextWithAvro.java
│       │       ├── ParquetToTextWithExample.java
│       │       ├── TextToParquetWithAvro.java
│       │       └── TextToParquetWithExample.java
│       └── test
│           ├── java
│           │   ├── ParquetMRWithAvroTest.java
│           │   ├── ParquetMRWithExampleTest.java
│           │   └── ParquetTest.java
│           └── resources
│               ├── NewStringPair.avsc
│               ├── ProjectedStringPair.avsc
│               ├── StringPair.avsc
│               └── fruit.txt
├── ch14-flume
│   ├── spool-to-hdfs-and-logger.properties
│   ├── spool-to-hdfs-avro.properties
│   ├── spool-to-hdfs-partitioned.properties
│   ├── spool-to-hdfs-tiered-load-balance.properties
│   ├── spool-to-hdfs-tiered.properties
│   ├── spool-to-hdfs.properties
│   └── spool-to-logger.properties
├── ch15-sqoop
│   ├── pom.xml
│   ├── src
│   │   └── main
│   │       └── java
│   │           ├── MaxWidgetId.java
│   │           ├── MaxWidgetIdGenericAvro.java
│   │           └── Widget.java
│   └── widgets
│       └── part-m-00000.avro
├── ch16-pig
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── grunt
│       │   │   ├── combine.grunt
│       │   │   ├── disambiguate.grunt
│       │   │   ├── flatten.grunt
│       │   │   ├── foreach.grunt
│       │   │   ├── group.grunt
│       │   │   ├── join.grunt
│       │   │   ├── max_temp.grunt
│       │   │   ├── missing.grunt
│       │   │   ├── multiquery.grunt
│       │   │   ├── null.grunt
│       │   │   ├── schema.grunt
│       │   │   ├── set.grunt
│       │   │   ├── sort.grunt
│       │   │   ├── store.grunt
│       │   │   ├── stream.grunt
│       │   │   ├── tuples.grunt
│       │   │   ├── types.grunt
│       │   │   └── udfs.grunt
│       │   ├── java
│       │   │   └── com
│       │   │       └── hadoopbook
│       │   │           └── pig
│       │   │               ├── CutLoadFunc.java
│       │   │               ├── IsGoodQuality.java
│       │   │               ├── Range.java
│       │   │               └── Trim.java
│       │   ├── pig
│       │   │   ├── comment_c-style.pig
│       │   │   ├── comment_single_line.pig
│       │   │   ├── max_temp.macro
│       │   │   ├── max_temp.pig
│       │   │   ├── max_temp_filter_stream.pig
│       │   │   ├── max_temp_filter_udf.pig
│       │   │   ├── max_temp_macro.pig
│       │   │   ├── max_temp_macro_import.pig
│       │   │   ├── max_temp_param.param
│       │   │   ├── max_temp_param.pig
│       │   │   ├── max_temp_station_name.pig
│       │   │   └── year_stats.pig
│       │   └── python
│       │       └── is_good_quality.py
│       └── test
│           └── java
│               └── com
│                   └── hadoopbook
│                       └── pig
│                           ├── IsGoodQualityTest.java
│                           └── RangeTest.java
├── ch17-hive
│   ├── pom.xml
│   └── src
│       └── main
│           ├── hive
│           │   ├── buckets.hive
│           │   ├── conversions.hive
│           │   ├── indexes.hive
│           │   ├── joins.hive
│           │   ├── mapreduce.hive
│           │   ├── max_temp.hive
│           │   ├── multitable_insert.hive
│           │   ├── partitions.hive
│           │   ├── regex_serde.hive
│           │   ├── set.hive
│           │   ├── sort.hive
│           │   ├── storage.hive
│           │   ├── types.hive
│           │   └── udfs.hive
│           ├── java
│           │   └── com
│           │       └── hadoopbook
│           │           └── hive
│           │               ├── Maximum.java
│           │               ├── Mean.java
│           │               └── Strip.java
│           └── python
│               ├── is_good_quality.py
│               └── max_temperature_reduce.py
├── ch18-crunch
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── assembly
│       │   │   └── hadoop-job.xml
│       │   └── java
│       │       └── crunch
│       │           ├── AvroGenericMaxTemperatureCrunch.java
│       │           ├── JoinRecordWithStationNameCrunch.java
│       │           ├── MaxTemperatureByStationNameCrunch.java
│       │           ├── MaxTemperatureCrunch.java
│       │           ├── MaxTemperatureCrunchWithShutdownHook.java
│       │           ├── MaxTemperatureUsingSecondarySortCrunch.java
│       │           ├── MaxTemperatureWithCompressionCrunch.java
│       │           ├── MaxTemperatureWithCountersCrunch.java
│       │           ├── MaxTemperatureWithMultipleInputsCrunch.java
│       │           ├── MetOfficeRecordParser.java
│       │           ├── NcdcRecordParser.java
│       │           ├── NcdcStationMetadataParser.java
│       │           ├── SortByTemperatureCrunch.java
│       │           └── SplitCrunch.java
│       └── test
│           ├── java
│           │   └── crunch
│           │       ├── CheckpointTest.java
│           │       ├── CountValuesFn.java
│           │       ├── CustomDoFn.java
│           │       ├── InversePairFn.java
│           │       ├── JoinTest.java
│           │       ├── MaterializeTest.java
│           │       ├── NonSerializableOuterClass.java
│           │       ├── ObjectReuseTest.java
│           │       ├── PCollections.java
│           │       ├── PageRankTest.java
│           │       ├── PipelineDebugTest.java
│           │       ├── PipelineExecutionTest.java
│           │       ├── PrimitiveOperationsTest.java
│           │       ├── SerializableFunctionsTest.java
│           │       ├── SortTest.java
│           │       ├── SourcesAndTargetsTest.java
│           │       ├── ToLowerFn.java
│           │       ├── TypesTest.java
│           │       └── WeatherRecord.java
│           └── resources
│               ├── A
│               ├── B
│               ├── fruit.txt
│               ├── ints.txt
│               ├── log4j.properties
│               ├── numbers.seq
│               ├── sample.txt
│               ├── set1.txt
│               ├── set2.txt
│               └── urls.txt
├── ch19-spark
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── java
│       │   │   └── MaxTemperatureSpark.java
│       │   ├── python
│       │   │   └── MaxTemperature.py
│       │   └── scala
│       │       ├── MaxTemperature.scala
│       │       └── MaxTemperatureWithPlacement.scala
│       └── test
│           ├── avro
│           │   ├── IntWrapper.avsc
│           │   └── WeatherRecord.avsc
│           ├── java
│           │   └── SimpleTest.java
│           ├── resources
│           │   ├── fruit.txt
│           │   ├── log4j.properties
│           │   ├── numbers.seq
│           │   ├── quangle.txt
│           │   └── set2.txt
│           └── scala
│               ├── CustomKryoRegistrator.scala
│               ├── DataSerializationTest.scala
│               ├── FunctionSerializationTest.scala
│               ├── RDDCreationTest.scala
│               ├── ReflectWeatherRecord.scala
│               ├── SharedDataTest.scala
│               ├── TransformationsAndActionsTest.scala
│               └── WordCountHistogramTest.scala
├── ch20-hbase
│   ├── pom.xml
│   └── src
│       └── main
│           └── java
│               ├── ExampleClient.java
│               ├── HBaseStationImporter.java
│               ├── HBaseStationQuery.java
│               ├── HBaseTemperatureBulkImporter.java
│               ├── HBaseTemperatureDirectImporter.java
│               ├── HBaseTemperatureImporter.java
│               ├── HBaseTemperatureQuery.java
│               ├── NewExampleClient.java
│               ├── NewHBaseStationImporter.java
│               ├── NewHBaseStationQuery.java
│               ├── NewHBaseTemperatureQuery.java
│               ├── RowKeyConverter.java
│               └── SimpleRowCounter.java
├── ch21-zk
│   ├── pom.xml
│   └── src
│       └── main
│           ├── java
│           │   ├── ActiveKeyValueStore.java
│           │   ├── ConfigUpdater.java
│           │   ├── ConfigWatcher.java
│           │   ├── ConnectionWatcher.java
│           │   ├── CreateGroup.java
│           │   ├── DeleteGroup.java
│           │   ├── JoinGroup.java
│           │   ├── ListGroup.java
│           │   ├── ResilientActiveKeyValueStore.java
│           │   └── ResilientConfigUpdater.java
│           └── sh
│               └── group.sh
├── ch22-case-studies
│   ├── pom.xml
│   └── src
│       └── main
│           └── java
│               ├── TrackStats.jr
│               └── fm
│                   └── last
│                       └── hadoop
│                           ├── io
│                           │   └── records
│                           │       └── TrackStats.java
│                           └── programs
│                               └── labs
│                                   └── trackstats
│                                       └── TrackStatisticsProgram.java
├── common
│   ├── pom.xml
│   └── src
│       ├── main
│       │   └── java
│       │       ├── JobBuilder.java
│       │       ├── MetOfficeRecordParser.java
│       │       ├── NcdcRecordParser.java
│       │       ├── NcdcStationMetadata.java
│       │       ├── NcdcStationMetadataParser.java
│       │       └── oldapi
│       │           ├── JobBuilder.java
│       │           ├── MetOfficeRecordParser.java
│       │           ├── NcdcRecordParser.java
│       │           ├── NcdcStationMetadata.java
│       │           └── NcdcStationMetadataParser.java
│       └── test
│           └── java
│               ├── MetOfficeRecordParserTest.java
│               ├── NcdcRecordParserTest.java
│               └── NcdcStationMetadataParserTest.java
├── conf
│   ├── hadoop
│   │   └── pseudo-distributed
│   │       ├── core-site.xml
│   │       ├── hdfs-site.xml
│   │       ├── mapred-site.xml
│   │       └── yarn-site.xml
│   ├── hadoop-cluster.template.xml
│   ├── hadoop-local.xml
│   ├── hadoop-localhost.xml
│   ├── pig
│   │   └── localhost
│   │       └── pig.properties
│   └── zookeeper
│       ├── cluster
│       │   └── zoo.cfg
│       ├── localhost
│       │   └── zoo.cfg
│       └── log4j.properties
├── hadoop-examples
│   └── pom.xml
├── hadoop-meta
│   └── pom.xml
├── input
│   ├── avro
│   │   └── pairs.avro
│   ├── badrecords
│   │   ├── a
│   │   ├── b
│   │   └── c
│   ├── docs
│   │   ├── 1400-8.txt
│   │   └── quangle.txt
│   ├── fileglob
│   │   ├── 2007
│   │   │   └── 12
│   │   │       ├── 30
│   │   │       │   ├── data-2007-12-30
│   │   │       │   └── data[2007-12-30]
│   │   │       └── 31
│   │   │           └── data-2007-12-31
│   │   └── 2008
│   │       └── 01
│   │           └── 01
│   │               └── data-2008-01-01
│   ├── fileinput
│   │   ├── a
│   │   └── dir
│   │       └── b
│   ├── hive
│   │   ├── README
│   │   ├── dummy.txt
│   │   ├── joins
│   │   │   ├── sales.txt
│   │   │   └── things.txt
│   │   ├── partitions
│   │   │   ├── file1
│   │   │   ├── file2
│   │   │   ├── file3
│   │   │   ├── file4
│   │   │   ├── file5
│   │   │   └── file6
│   │   ├── tables
│   │   │   ├── users.txt
│   │   │   └── users_extended.txt
│   │   ├── tmp.txt
│   │   ├── types
│   │   │   ├── complex.txt
│   │   │   └── nested.txt
│   │   └── udfs
│   │       ├── arrays.txt
│   │       ├── fruit.txt
│   │       ├── max1.txt
│   │       └── max2.txt
│   ├── metoffice
│   │   ├── aberporthdata.txt
│   │   ├── armaghdata.txt
│   │   ├── bradforddata.txt
│   │   ├── braemardata.txt
│   │   ├── cambridgedata.txt
│   │   ├── cardiffdata.txt
│   │   ├── durhamdata.txt
│   │   ├── eastbournedata.txt
│   │   ├── greenwichdata.txt
│   │   ├── hurndata.txt
│   │   ├── lerwickdata.txt
│   │   ├── leucharsdata.txt
│   │   ├── newtonriggdata.txt
│   │   ├── oxforddata.txt
│   │   ├── paisleydata.txt
│   │   ├── ringwaydata.txt
│   │   ├── rossonwyedata.txt
│   │   ├── shawburydata.txt
│   │   ├── sheffielddata.txt
│   │   ├── southamptondata.txt
│   │   ├── stmawgandata.txt
│   │   ├── stornowaydata.txt
│   │   ├── suttonbonningtondata.txt
│   │   ├── tireedata.txt
│   │   ├── valleydata.txt
│   │   └── yeoviltondata.txt
│   ├── ncdc
│   │   ├── all
│   │   │   ├── 1901.gz
│   │   │   └── 1902.gz
│   │   ├── metadata
│   │   │   ├── ish-history.txt
│   │   │   └── stations-fixed-width.txt
│   │   ├── micro
│   │   │   └── sample.txt
│   │   ├── micro-tab
│   │   │   ├── sample.txt
│   │   │   ├── sample2.txt
│   │   │   └── sample_corrupt.txt
│   │   ├── sample.txt
│   │   └── sample.txt.gz
│   ├── pig
│   │   ├── combine
│   │   │   ├── A
│   │   │   └── B
│   │   ├── corrupt
│   │   │   └── missing_fields
│   │   ├── foreach
│   │   │   └── A
│   │   ├── group
│   │   │   └── A
│   │   ├── join
│   │   │   ├── A
│   │   │   └── B
│   │   ├── multiquery
│   │   │   └── A
│   │   ├── nested
│   │   │   ├── A
│   │   │   └── B
│   │   ├── pairwise
│   │   │   └── postings
│   │   ├── schema
│   │   │   └── A
│   │   ├── sort
│   │   │   └── A
│   │   ├── tuples
│   │   │   └── A
│   │   ├── types
│   │   │   ├── A
│   │   │   ├── B
│   │   │   ├── C
│   │   │   └── one
│   │   └── udfs
│   │       └── A
│   ├── smallfiles
│   │   ├── a
│   │   ├── b
│   │   ├── c
│   │   ├── d
│   │   ├── e
│   │   └── f
│   └── wikipedia
│       ├── example.xml
│       └── sample.xml
├── pom.xml
├── snippet
│   ├── README
│   ├── bin
│   │   ├── check_expected.sh
│   │   ├── check_manuscript.py
│   │   ├── check_manuscript.sh
│   │   ├── generate_listings.sh
│   │   ├── grunter.sh
│   │   ├── hiver.sh
│   │   ├── phragmite_db.pl
│   │   ├── phragmite_hive.py
│   │   └── phragmite_pig.py
│   ├── conf
│   │   ├── local
│   │   │   ├── capacity-scheduler.xml
│   │   │   ├── configuration.xsl
│   │   │   ├── container-executor.cfg
│   │   │   ├── core-site.xml
│   │   │   ├── hadoop-env.cmd
│   │   │   ├── hadoop-env.sh
│   │   │   ├── hadoop-metrics.properties
│   │   │   ├── hadoop-metrics2.properties
│   │   │   ├── hadoop-policy.xml
│   │   │   ├── hdfs-site.xml
│   │   │   ├── httpfs-env.sh
│   │   │   ├── httpfs-log4j.properties
│   │   │   ├── httpfs-signature.secret
│   │   │   ├── httpfs-site.xml
│   │   │   ├── log4j.properties
│   │   │   ├── mapred-env.cmd
│   │   │   ├── mapred-env.sh
│   │   │   ├── mapred-queues.xml.template
│   │   │   ├── mapred-site.xml
│   │   │   ├── mapred-site.xml.template
│   │   │   ├── slaves
│   │   │   ├── ssl-client.xml.example
│   │   │   ├── ssl-server.xml.example
│   │   │   ├── yarn-env.cmd
│   │   │   ├── yarn-env.sh
│   │   │   └── yarn-site.xml
│   │   └── pseudo
│   │       ├── capacity-scheduler.xml
│   │       ├── capacity-scheduler.xml.old
│   │       ├── configuration.xsl
│   │       ├── container-executor.cfg
│   │       ├── core-site.xml
│   │       ├── fair-scheduler.xml
│   │       ├── hadoop-env.cmd
│   │       ├── hadoop-env.sh
│   │       ├── hadoop-metrics.properties
│   │       ├── hadoop-metrics2.properties
│   │       ├── hadoop-policy.xml
│   │       ├── hdfs-site.xml
│   │       ├── httpfs-env.sh
│   │       ├── httpfs-log4j.properties
│   │       ├── httpfs-signature.secret
│   │       ├── httpfs-site.xml
│   │       ├── log4j.properties
│   │       ├── mapred-env.cmd
│   │       ├── mapred-env.sh
│   │       ├── mapred-queues.xml.template
│   │       ├── mapred-site.xml
│   │       ├── mapred-site.xml.template
│   │       ├── slaves
│   │       ├── ssl-client.xml.example
│   │       ├── ssl-server.xml.example
│   │       ├── yarn-env.cmd
│   │       ├── yarn-env.sh
│   │       └── yarn-site.xml
│   ├── expected
│   │   └── ch11
│   │       └── grunt
│   │           ├── combine_schema.xml
│   │           ├── combine_union.xml
│   │           ├── foreach_generate.xml
│   │           ├── group_all.xml
│   │           ├── group_dump.xml
│   │           ├── group_expression.xml
│   │           ├── join_cogroup.xml
│   │           ├── join_cogroup_flatten.xml
│   │           ├── join_cogroup_inner.xml
│   │           ├── join_cogroup_join.xml
│   │           ├── join_dump.xml
│   │           ├── join_frj.xml
│   │           ├── join_join.xml
│   │           ├── max_temp_describe_records.xml
│   │           ├── max_temp_dump_grouped_records.xml
│   │           ├── max_temp_dump_records.xml
│   │           ├── max_temp_filter_records.xml
│   │           ├── max_temp_load.xml
│   │           ├── max_temp_max_temp.xml
│   │           ├── max_temp_result.xml
│   │           ├── missing_fields.xml
│   │           ├── null_corrupt.xml
│   │           ├── null_count.xml
│   │           ├── null_dump.xml
│   │           ├── null_split.xml
│   │           ├── null_undetected.xml
│   │           ├── schema_absent.xml
│   │           ├── schema_absent_projected.xml
│   │           ├── schema_names_only.xml
│   │           ├── schema_one_type_only.xml
│   │           ├── schema_types.xml
│   │           ├── set_debug_on.xml
│   │           ├── sort_dump.xml
│   │           ├── sort_limit.xml
│   │           ├── sort_no_order.xml
│   │           ├── sort_order.xml
│   │           ├── store_colon_delimited.xml
│   │           ├── stream_cut.xml
│   │           ├── udfs_invoke_long.xml
│   │           ├── udfs_invoke_short.xml
│   │           ├── udfs_load.xml
│   │           ├── udfs_register.xml
│   │           └── udfs_schema.xml
│   ├── pom.xml
│   └── src
│       └── test
│           ├── java
│           │   └── ExamplesIT.java
│           └── resources
│               ├── copyoutput.sh
│               └── setup.sh
└── src-structure.txt

339 directories, 776 files


```