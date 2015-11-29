```java
import java.util.*;
// import java.util.Arrays;
// import java.util.ArrayList;
public class JavaSkill4Interview{
	public static void main(String[] args) {
		//String
		String s = "abcd";
		s.charAt(0);
		s.length();
		s.substring(1,2);// "b" the second index is exclusive
		s.substring(1); //"bcd"
		s.equals("a"); // false
		s = s.trim();
		s.indexOf('a'); // 0
		s.indexOf('a', 1);//-1
		s.indexOf("bc",1); //1
		s.lastIndexOf('a');//0
		s = "123";
		s.toCharArray();
		Integer.valueOf(s); // returns an Integer object
		Integer.parseInt(s); // returns an int primitive
		String.valueOf(s); // integer to string
		StringBuilder sb = new StringBuilder();
		sb.append("a");
		sb.insert(0, "b");
		sb.deleteCharAt(sb.length()-1);
		sb.reverse();
		sb.toString();
		// System.out.println(sb);
		//Array
		int[] a = new int[10];
		int l = a.length;
		char[] b = {'a','b'};
		System.out.println(b[1]);
		String ss="";
		ss = ss.copyValueOf(b);
		int[][] c = new int[10][10];
		int max = Integer.MAX_VALUE;
		int min = Integer.MIN_VALUE;
		Arrays.sort(a);
		//List; List is an interface; ArrayList implements List
		List<Integer> list = new ArrayList<Integer>();
		ArrayList<Integer> list1 = new ArrayList<>();
		List<List<Integer>> list2 = new ArrayList<>();
		list.add(0);
		list.add(0,2); //position, value
		// for(int i:list){
		// 	System.out.println(i);
		// }
		list.forEach((i)->System.out.println(i));
		list.size(); // not length()!!!
		list.get(0); //2; cannot use list[0]
		list.remove(0);
		System.out.println(list.get(0));
		Collections.sort(list);
		Collections.sort(list, Collections.reverseOrder());
		Collections.sort(list, new Comparator<Integer>(){
			@Override
			public int compare(Integer o1, Integer o2){
				return o1.compareTo(o2); //ascending;
				// return o2.compareTo(o1); //descending;
			}
		});
		//lambda
		Collections.sort(list, (Integer o1, Integer o2)->o1.compareTo(o2));
		// In Java 8, the List interface is supports the sort method directly, no need to use Collections.sort anymore.
		list.sort((Integer o1, Integer o2)->o1-o2);
		Comparator<Integer> cptr = (Integer o1, Integer o2)->o1-o2;
		list.sort(cptr);
		//Stack
		Stack<Integer> st = new Stack<>();
		st.push(0);
		st.push(1);
		int peek = st.peek();
		System.out.println(peek);
		peek = st.pop(); 
		st.isEmpty();
		st.size();
		// Queue
		Queue<Integer> q = new LinkedList<>();
		q.add(0);
		q.add(1);
		int peekq = q.peek();
		System.out.println(peekq);
		q.remove();
		q.isEmpty();
		q.size();
		// HashSet
		HashSet<Integer> set = new HashSet<>();
		set.add(0);
		set.remove(0);
		if(set.contains(0)){};
		set.size(); set.isEmpty();
		//HashMap
		HashMap<Character, Integer> mp = new HashMap<>();
		mp.put('c',1);
		mp.get('c');
		if(mp.containsKey('a')){};
		if(mp.containsValue(1)){};
		for(Character cc : mp.keySet()){};
		for(Integer i : mp.values()){};
		mp.isEmpty();
		mp.size();
		//min queue
		// PriorityQueue<Integer> pq = new PriorityQueue<>();
		Comparator<Integer> cptr1 = (Integer i1, Integer i2)->(i2-i1);
		//max queue
		// PriorityQueue<Integer> pq = new PriorityQueue<>(cptr.reversed());
		//max queue
		PriorityQueue<Integer> pq = new PriorityQueue<>(cptr1);
		pq.add(100);
		pq.add(10);
		System.out.println(pq.peek());
		pq.remove();
		pq.size();
		pq.isEmpty();

		List<HashSet<Integer>> listOfHashSet = new ArrayList<>(10);
        for(int i=0; i<10; ++i) listOfHashSet.add(new HashSet<>());
	}
}
```