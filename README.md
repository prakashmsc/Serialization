# Serialization
package com.serialisation;

import java.io.*;
public class Persist implements Serializable {
  int id;
	 String name;
	Persist(int id,String name){
		this.id=id;
		this.name=name;
		
	}

	public static void main(String[] args) throws IOException {
		// TODO Auto-generated method stub
		Persist p=new Persist(24,"prakash");
		Persist p1=new Persist(23,"shanmuga");
		Persist p2=new Persist(22,"thirus");
		Persist p3=new Persist(21,"hari");
		FileOutputStream fout=new FileOutputStream("D:/b.txt");
		ObjectOutputStream out=new ObjectOutputStream(fout);
		out.writeObject(p);
		out.writeObject(p1);
		out.writeObject(p2);
		out.writeObject(p3);
		out.flush();
		out.close();
		System.out.println("success");
	}

	

}
package com.serialisation;

import java.io.*;

public class Depersist{

	public static void main(String[] args) throws Exception {
		// TODO Auto-generated method stub
		FileInputStream fout=new FileInputStream("D:/b.txt");
		ObjectInputStream in=new ObjectInputStream(fout);
		Persist p=(Persist)in.readObject();
		Persist p1=(Persist)in.readObject();
		Persist p2=(Persist)in.readObject();
		Persist p3=(Persist)in.readObject();
		in.close();
		System.out.println("the person Name is: "+" "+p.name+" "+p1.name+" "+p2.name+" "+p3.name);
		System.out.println("the person id is: "+p.id);

	}

}
