---
title:  "Pooling Operations"
mathjax: true
layout: post
categories: media
---

## Generalized Mean Pooling
<img width="247" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/548316ea-dd19-40d4-96a1-f07db14ddfab">

* Generalized Mean Pooling (GeM) tính trung bình tổng quát của mỗi kênh trong một tensor. GeM là một sự tổng quát hóa của phép lọc trung bình thường được sử dụng trong các mạng phân loại và của lớp max-pooling không gian.
## Global Average Pooling
* Global Average Pooling là một phép gom nhóm được thiết kế để thay thế các lớp kết nối đầy đủ trong CNN cổ điển. Ý tưởng là tạo ra một bản đồ đặc trưng cho mỗi danh mục tương ứng của nhiệm vụ phân loại trong lớp mlpconv cuối cùng. Thay vì thêm các lớp kết nối đầy đủ lên trên các bản đồ đặc trưng, chúng ta lấy trung bình của mỗi bản đồ đặc trưng, và vectơ kết quả được đưa trực tiếp vào lớp softmax.

•	00000000,06-26-2011,4000001,040.33,Exercise & Fitness,Cardio Machine Accessories,Clarksville,Tennessee,credit
•	00000001,05-26-2011,4000002,198.44,Exercise & Fitness,Weightlifting Gloves,Long Beach,California,credit
•	00000002,06-01-2011,4000002,005.58,Exercise & Fitness,Weightlifting Machine Accessories,Anaheim,California,credit
•	00000003,06-05-2011,4000003,198.19,Gymnastics,Gymnastics Rings,Milwaukee,Wisconsin,credit
•	00000004,12-17-2011,4000002,098.81,Team Sports,Field Hockey,Nashville  ,Tennessee,credit
•	00000005,02-14-2011,4000004,193.63,Outdoor Recreation,Camping & Backpacking & Hiking,Chicago,Illinois,credit
•	00000006,10-28-2011,4000005,027.89,Puzzles,Jigsaw Puzzles,Charleston,South Carolina,credit
•	00000007,07-14-2011,4000006,096.01,Outdoor Play Equipment,Sandboxes,Columbus,Ohio,credit
•	00000008,01-17-2011,4000006,010.44,Winter Sports,Snowmobiling,Des Moines,Iowa,credit
•	00000009,05-17-2011,4000006,152.46,Jumping,Bungee Jumping,St. Petersburg,Florida,credit
•	00000010,05-29-2011,4000007,180.28,Outdoor Recreation,Archery,Reno,Nevada,credit
•	00000011,06-18-2011,4000009,121.39,Outdoor Play Equipment,Swing Sets,Columbus,Ohio,credit
•	00000012,02-08-2011,4000009,041.52,Indoor Games,Bowling,San Francisco,California,credit
•	00000013,03-13-2011,4000010,107.80,Team Sports,Field Hockey,Honolulu  ,Hawaii,credit
•	00000014,02-25-2011,4000010,036.81,Gymnastics,Vaulting Horses,Los Angeles,California,credit
•	00000015,10-20-2011,4000001,137.64,Combat Sports,Fencing,Honolulu  ,Hawaii,credit
•	00000016,05-28-2011,4000010,035.56,Exercise & Fitness,Free Weight Bars,Columbia,South Carolina,credit
•	00000017,10-18-2011,4000008,075.55,Water Sports,Scuba Diving & Snorkeling,Omaha,Nebraska,credit
•	00000018,11-18-2011,4000008,088.65,Team Sports,Baseball,Salt Lake City,Utah,credit
•	00000019,08-28-2011,4000008,051.81,Water Sports,Life Jackets,Newark,New Jersey,credit
•	00000020,06-29-2011,4000005,041.55,Exercise & Fitness,Weightlifting Belts,New Orleans,Louisiana,credit
•	00000021,02-14-2011,4000005,045.79,Air Sports,Parachutes,New York,New York,credit
•	00000022,10-10-2011,4000009,019.64,Water Sports,Kitesurfing,Saint Paul,Minnesota,credit
•	00000023,05-02-2011,4000009,099.50,Gymnastics,Gymnastics Rings,Springfield,Illinois,credit
•	00000024,06-10-2011,4000003,151.20,Water Sports,Surfing,Plano,Texas,credit
•	00000025,10-14-2011,4000009,144.20,Indoor Games,Darts,Phoenix,Arizona,credit
•	00000026,10-11-2011,4000009,031.58,Combat Sports,Wrestling,Orange,California,credit
•	00000027,09-29-2011,4000010,066.40,Games,Mahjong,Fremont,California,credit
•	00000028,05-12-2011,4000008,079.78,Team Sports,Cricket,Lexington,Kentucky,credit
•	00000029,06-03-2011,4000001,126.90,Outdoor Recreation,Hunting,Phoenix,Arizona,credit
•	00000030,03-14-2011,4000001,047.05,Water Sports,Swimming,Lincoln,Nebraska,credit
•	00000031,11-28-2011,4000008,005.03,Games,Dice & Dice Sets,Los Angeles,California,credit
•	00000032,01-29-2011,4000008,020.13,Team Sports,Soccer,Springfield,Illinois,credit
•	00000033,06-15-2011,4000008,154.15,Outdoor Recreation,Lawn Games,Nashville  ,Tennessee,credit
•	00000034,05-06-2011,4000008,098.96,Team Sports,Indoor Volleyball,Atlanta,Georgia,credit
•	00000035,04-12-2011,4000008,185.26,Games,Board Games,Centennial,Colorado,credit
•	00000036,10-13-2011,4000007,035.66,Team Sports,Football,Saint Paul,Minnesota,credit
•	00000037,04-19-2011,4000007,020.20,Outdoor Recreation,Shooting Games,San Diego,California,credit
•	00000038,08-05-2011,4000007,150.60,Outdoor Recreation,Camping & Backpacking & Hiking,Hampton  ,Virginia,credit
•	00000039,03-12-2011,4000006,174.36,Outdoor Play Equipment,Swing Sets,Pittsburgh,Pennsylvania,credit
•	00000040,11-07-2011,4000005,165.10,Team Sports,Cheerleading,Reno,Nevada,credit
•	00000041,04-16-2011,4000004,028.11,Indoor Games,Bowling,Westminster,Colorado,cash
•	00000042,09-10-2011,4000004,038.52,Outdoor Recreation,Tetherball,Denton,Texas,cash
•	00000043,04-22-2011,4000004,032.34,Water Sports,Water Polo,Las Vegas,Nevada,cash
•	00000044,09-11-2011,4000001,135.37,Water Sports,Surfing,Seattle,Washington,credit
•	00000045,11-27-2011,4000001,090.04,Exercise & Fitness,Abdominal Equipment,Honolulu  ,Hawaii,credit
•	00000046,05-27-2011,4000001,052.29,Gymnastics,Vaulting Horses,Cleveland,Ohio,credit
•	00000047,10-23-2011,4000008,100.10,Outdoor Play Equipment,Swing Sets,Everett,Washington,credit
•	00000048,09-27-2011,4000007,157.94,Exercise & Fitness,Exercise Bands,Philadelphia,Pennsylvania,credit
•	00000049,07-12-2011,4000010,144.59,Jumping,Jumping Stilts,Cambridge,Massachusetts,credit
•	00000050,10-20-2011,4000010,055.93,Jumping,Pogo Sticks,Everett,Washington,credit
•	00000051,02-17-2011,4000002,032.65,Water Sports,Life Jackets,Columbus,Georgia,cash
•	00000052,02-04-2011,4000005,044.82,Outdoor Play Equipment,Lawn Water Slides,Hampton  ,Virginia,cash
•	00000053,06-12-2011,4000004,044.46,Water Sports,Scuba Diving & Snorkeling,Charleston,South Carolina,cash
•	00000054,10-03-2011,4000007,154.87,Outdoor Recreation,Running,Long Beach,California,credit
•	00000055,12-16-2011,4000006,106.11,Water Sports,Swimming,New York,New York,credit
•	00000056,06-21-2011,4000002,176.63,Outdoor Recreation,Geocaching,Boston,Massachusetts,credit
•	00000057,12-20-2011,4000003,178.20,Outdoor Recreation,Skating,San Jose,California,credit
•	00000058,12-29-2011,4000002,194.86,Water Sports,Windsurfing,Oklahoma City,Oklahoma,credit
•	00000059,11-07-2011,4000001,021.43,Winter Sports,Snowboarding,Philadelphia,Pennsylvania,cash




--------------
import java.io.IOException;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.MultipleInputs;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
 
 public class ReduceJoin {
 public static class CustsMapper extends Mapper <Object, Text, Text, Text>
 {
 public void map(Object key, Text value, Context context)
 throws IOException, InterruptedException 
 {
 String record = value.toString();
 String[] parts = record.split(",");
 context.write(new Text(parts[0]), new Text("cust   " + parts[1]));
 }
 }
 
 public static class TxnsMapper extends Mapper <Object, Text, Text, Text>
 {
 public void map(Object key, Text value, Context context) 
 throws IOException, InterruptedException 
 {
 String record = value.toString();
 String[] parts = record.split(",");
 context.write(new Text(parts[2]), new Text("tnxn   " + parts[3]));
 }
 }
 
 public static class ReduceJoinReducer extends Reducer <Text, Text, Text, Text>
 {
 public void reduce(Text key, Iterable<Text> values, Context context)
 throws IOException, InterruptedException 
 {
 String name = "";
 double total = 0.0;
 int count = 0;
 for (Text t : values) 
 { 
 String parts[] = t.toString().split("   ");
 if (parts[0].equals("tnxn")) 
 {
 count++;
 total += Float.parseFloat(parts[1]);
 } 
 else if (parts[0].equals("cust")) 
 {
 name = parts[1];
 }
 }
 String str = String.format("%d %f", count, total);
 context.write(new Text(name), new Text(str));
 }
 }
 
 public static void main(String[] args) throws Exception {
 Configuration conf = new Configuration();
 Job job = new Job(conf, "Reduce-side join");
 job.setJarByClass(ReduceJoin.class);
 job.setReducerClass(ReduceJoinReducer.class);
 job.setOutputKeyClass(Text.class);
 job.setOutputValueClass(Text.class);
  
 MultipleInputs.addInputPath(job, new Path(args[0]),TextInputFormat.class, CustsMapper.class);
 MultipleInputs.addInputPath(job, new Path(args[1]),TextInputFormat.class, TxnsMapper.class);
 Path outputPath = new Path(args[2]);
  
 FileOutputFormat.setOutputPath(job, outputPath);
 outputPath.getFileSystem(conf).delete(outputPath);
 System.exit(job.waitForCompletion(true) ? 0 : 1);
 }
 }



 ----------------
 import java.io.*;
import java.util.*;
import java.net.URI;
  


import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Reducer.Context;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
 
 public class Transanalysis1 {
 

 public static class TransMapper extends Mapper <Object, Text, Text, Text>
 {
	 // user map to keep the userId-userName
	 private Map<Integer, String> userMap = new HashMap<>();
	 
public void setup(Context context) throws IOException, InterruptedException
{	
	  try (BufferedReader br = new BufferedReader(new FileReader("cust.txt"))) {
		   String line;
		   while ((line = br.readLine()) != null) {
		    String columns[] = line.split(",");
			//String id = 
			//String name = 
		    userMap.put(Integer.parseInt(columns[0]), columns[1]);
		   }
		  } catch (IOException e) {
		   e.printStackTrace();
		  }
}


 public void map(Object key, Text value, Context context) 
 throws IOException, InterruptedException 
 {
		String record = value.toString().trim();
		String[] parts = record.split(",");
		//
		String gametype = parts[4];
		String id = parts[2];
		String name = userMap.get(Integer.parseInt(id));
		String amount = parts[3];
		//
		context.write(new Text(gametype), new Text(name + " " + amount));
 }
 }
 
 public static class TransReducer extends Reducer <Text, Text, Text, Text>
 {
	 public void reduce(Text key, Iterable<Text> values, Context context)
			 throws IOException, InterruptedException 
			 {
				 double total = 0.0;
				 //
				 String IDlist = "";
				 for (Text t : values) {
					 String[] parts = t.toString().trim().split(" ");
					 //
					 total += Float.parseFloat(parts[1]);
					 IDlist += parts[0] + ",";
				 }
				 context.write(key, new Text("["+IDlist+"]" + "  " + Double.toString(total)));
			 }
 }
 
 public static void main(String[] args) throws Exception {
 Configuration conf = new Configuration();
 Job job = new Job(conf, "Mapside Join");
 job.setJarByClass(Transanalysis1.class);
 job.setMapperClass(TransMapper.class);
 job.setReducerClass(TransReducer.class);
 job.setOutputKeyClass(Text.class);
 job.setOutputValueClass(Text.class);
 // Setting reducer to zero
// job.setNumReduceTasks(0);
  
 
 try {
	  //
     job.addCacheFile(new URI("hdfs://localhost:8020/mycache/cust.txt"));
 }
 catch (Exception e) {
     System.out.println("File Not Added");
     System.exit(1);
 }
 
 FileInputFormat.addInputPath(job, new Path(args[0]));
 FileOutputFormat.setOutputPath(job, new Path(args[1]));
 System.exit(job.waitForCompletion(true) ? 0 : 1);
 }
 }

 ------------------
 import java.io.*;
import java.util.*;
import java.net.URI;
  





import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Reducer.Context;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
 
 public class assignment2 {
 

 public static class TransMapper extends Mapper <Object, Text, Text, Text>
 {
	 // user map to keep the userId-userName
	 private Map<Integer, String> userMap = new HashMap<>();
	 
public void setup(Context context) throws IOException, InterruptedException
{	
	  try (BufferedReader br = new BufferedReader(new FileReader("cust.txt"))) {
		   String line;
		   while ((line = br.readLine()) != null) {
		    String columns[] = line.split(",");
			String id = columns[0];
			String name = columns[1];
			String age = columns[3];
			
		    //userMap.put(Integer.parseInt(columns[0]), columns[1]);
		    userMap.put(Integer.parseInt(id), age);
		   }
		  } catch (IOException e) {
		   e.printStackTrace();
		  }
}


 public void map(Object key, Text value, Context context) 
 throws IOException, InterruptedException 
 {
		String record = value.toString().trim();
		String[] parts = record.split(",");
		
		String gametype = parts[4];
		String id = parts[2];
		String age = userMap.get(Integer.parseInt(id));
		//String amount = parts[3];
		
		context.write(new Text(gametype), new Text(age));
 }
 }

 public static class TransReducer extends Reducer <Text, Text, Text, Text>
 {
	 public void reduce(Text key, Iterable<Text> values, Context context)
			 throws IOException, InterruptedException 
			 {
				 double min = 1000.0;
				 double max = 0.0;
				 double total = 0.0;
				 double count = 0.0;
				 
				 
				 for (Text t : values) {
					 String[] parts = t.toString().trim().split(";");
					 double _age = Double.parseDouble(parts[0]);
					 
					 if (_age < min){
						 min = _age;
					 }
					 if (_age > max){
						 max = _age;
					 }
					 total += _age;
					 count += 1;
					 
				 }

			        if (count > 0) {
			            double avg = total / count;
			            context.write(key, new Text("[Min: " + min + " Max: " + max + " Avg: " + avg + "]"));
			        }			 
			 }
 }
 
 public static void main(String[] args) throws Exception {
 Configuration conf = new Configuration();
 Job job = new Job(conf, "Mapside Join");
 job.setJarByClass(assignment2.class);
 job.setMapperClass(TransMapper.class);
 job.setReducerClass(TransReducer.class);
 job.setOutputKeyClass(Text.class);
 job.setOutputValueClass(Text.class);
 // Setting reducer to zero
// job.setNumReduceTasks(0);
  
 
 try {
	  
     job.addCacheFile(new URI("hdfs://localhost:8020/mycache/cust.txt"));
 }
 catch (Exception e) {
     System.out.println("File Not Added");
     System.exit(1);
 }
 
 FileInputFormat.addInputPath(job, new Path(args[0]));
 FileOutputFormat.setOutputPath(job, new Path(args[1]));
 System.exit(job.waitForCompletion(true) ? 0 : 1);
 }
 }


--------------------
reduce join

import java.io.*;
import java.util.*;
import java.net.URI;
  





import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Reducer.Context;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
 
 public class assignment2 {
 

 public static class TransMapper extends Mapper <Object, Text, Text, Text>
 {
	 // user map to keep the userId-userName
	 private Map<Integer, String> userMap = new HashMap<>();
	 
public void setup(Context context) throws IOException, InterruptedException
{	
	  try (BufferedReader br = new BufferedReader(new FileReader("cust.txt"))) {
		   String line;
		   while ((line = br.readLine()) != null) {
		    String columns[] = line.split(",");
			String id = columns[0];
			String name = columns[1];
			String age = columns[3];
			\\
		    //userMap.put(Integer.parseInt(columns[0]), columns[1]);
		    userMap.put(Integer.parseInt(id), age);
		   }
		  } catch (IOException e) {
		   e.printStackTrace();
		  }
}


 public void map(Object key, Text value, Context context) 
 throws IOException, InterruptedException 
 {
		String record = value.toString().trim();
		String[] parts = record.split(",");
		\\
		String gametype = parts[4];
		String id = parts[2];
		String age = userMap.get(Integer.parseInt(id));
		//String amount = parts[3];
		\\
		context.write(new Text(gametype), new Text(age));
 }
 }

 public static class TransReducer extends Reducer <Text, Text, Text, Text>
 {
	 public void reduce(Text key, Iterable<Text> values, Context context)
			 throws IOException, InterruptedException 
			 {
				 double min = 1000.0;
				 double max = 0.0;
				 double total = 0.0;
				 double count = 0.0;
				 
				 
				 for (Text t : values) {
					 String[] parts = t.toString().trim().split(";");
					 double _age = Double.parseDouble(parts[0]);
					 
					 if (_age < min){
						 min = _age;
					 }
					 if (_age > max){
						 max = _age;
					 }
					 total += _age;
					 count += 1;
					
				 }

			        if (count > 0) {
			            double avg = total / count;
			            context.write(key, new Text("[Min: " + min + " Max: " + max + " Avg: " + avg + "]"));
			        }			 
			 }
 }
 
 public static void main(String[] args) throws Exception {
 Configuration conf = new Configuration();
 Job job = new Job(conf, "Mapside Join");
 job.setJarByClass(assignment2.class);
 job.setMapperClass(TransMapper.class);
 job.setReducerClass(TransReducer.class);
 job.setOutputKeyClass(Text.class);
 job.setOutputValueClass(Text.class);
 // Setting reducer to zero
// job.setNumReduceTasks(0);
  
 
 try {
	\\
     job.addCacheFile(new URI("hdfs://localhost:8020/mycache/cust.txt"));
 }
 catch (Exception e) {
     System.out.println("File Not Added");
     System.exit(1);
 }
 
 FileInputFormat.addInputPath(job, new Path(args[0]));
 FileOutputFormat.setOutputPath(job, new Path(args[1]));
 System.exit(job.waitForCompletion(true) ? 0 : 1);
 }
 }

 -------------
 import java.io.*;
import java.util.*;
import java.net.URI;
  


import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Reducer.Context;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
 
 public class Transanalysis1 {
 

 public static class TransMapper extends Mapper <Object, Text, Text, Text>
 {
	 // user map to keep the userId-userName
	 private Map<Integer, String> userMap = new HashMap<>();
	 
public void setup(Context context) throws IOException, InterruptedException
{	
	  try (BufferedReader br = new BufferedReader(new FileReader("cust.txt"))) {
		   String line;
		   while ((line = br.readLine()) != null) {
		    String columns[] = line.split(",");
			//String id = 
			//String name = 
		    userMap.put(Integer.parseInt(columns[0]), columns[1]);
		   }
		  } catch (IOException e) {
		   e.printStackTrace();
		  }
}


 public void map(Object key, Text value, Context context) 
 throws IOException, InterruptedException 
 {
		String record = value.toString().trim();
		String[] parts = record.split(",");
		\\
		String gametype = parts[4];
		String id = parts[2];
		String name = userMap.get(Integer.parseInt(id));
		String amount = parts[3];
		\\
		context.write(new Text(gametype), new Text(name + " " + amount));
 }
 }
 
 public static class TransReducer extends Reducer <Text, Text, Text, Text>
 {
	 public void reduce(Text key, Iterable<Text> values, Context context)
			 throws IOException, InterruptedException 
			 {
				 double total = 0.0;
				 \\
				 String IDlist = "";
				 for (Text t : values) {
					 String[] parts = t.toString().trim().split(" ");
					 \\
					 total += Float.parseFloat(parts[1]);
					 IDlist += parts[0] + ",";
				 }
				 context.write(key, new Text("["+IDlist+"]" + "  " + Double.toString(total)));
			 }
 }
 
 public static void main(String[] args) throws Exception {
 Configuration conf = new Configuration();
 Job job = new Job(conf, "Mapside Join");
 job.setJarByClass(Transanalysis1.class);
 job.setMapperClass(TransMapper.class);
 job.setReducerClass(TransReducer.class);
 job.setOutputKeyClass(Text.class);
 job.setOutputValueClass(Text.class);
 // Setting reducer to zero
// job.setNumReduceTasks(0);
  
 
 try {
	  \\
     job.addCacheFile(new URI("hdfs://localhost:8020/mycache/cust.txt"));
 }
 catch (Exception e) {
     System.out.println("File Not Added");
     System.exit(1);
 }
 
 FileInputFormat.addInputPath(job, new Path(args[0]));
 FileOutputFormat.setOutputPath(job, new Path(args[1]));
 System.exit(job.waitForCompletion(true) ? 0 : 1);
 }
 }
