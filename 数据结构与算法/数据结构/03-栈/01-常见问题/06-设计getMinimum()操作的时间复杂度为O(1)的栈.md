# 设计getMinimum()操作的时间复杂度为O(1)的栈

> [!Tip]
> 
> 本节源代码见[Github链接🔗](https://github.com/MaxSolider/leetcode-algorithm/blob/main/structure/src/main/java/org/example/linkedlist/exercises/NthNodeFromEnd.java)

---

## 问题描述
如何设计一个栈，使得getMinimum()操作的时间复杂度为O(1)？

---

## 核心思路
创建一个辅助栈保存原栈中所有元素的最小值。在元素入原栈时，向辅助栈中同时入栈当前最小的元素值：
<img src="https://s1.ax1x.com/2022/11/10/zpqgc8.png">


---

## 实现代码
<details> 
	<summary>【👉🏻>>点击展开查看代码】</summary> 
	<pre>
		<code>
		/**  
		 * getMinimum()操作的时间复杂度为O(1)的栈  
		 *  
		 * @className: AdvancedStack  
		 * @author: Max Solider  
		 * @date: 2023-06-08 22:19  
		 */public class AdvancedStack {  
		  
		    /**  
		     * 原栈  
		     */  
		    private LLStack oStack = new LLStack();  
		  
		    /**  
		     * 最小栈  
		     */  
		    private LLStack mStack = new LLStack();  
		  
		    /**  
		     * 入栈操作(只有新入栈元素比栈内最小元素还小时，才在minStack中入栈)  
		     * @param data 待入栈元素  
		     */  
		    public void push(int data) {  
		        oStack.push(String.valueOf(data));  
		        if (mStack.isEmpty() || data < Integer.parseInt(mStack.top())) {  
		            mStack.push(String.valueOf(data));  
		        }  
		    }  
		  
		    /**  
		     * 出栈元素(只有原栈顶元素和最小栈顶元素相等时，minStack中元素才出栈)  
		     */    public String pop() {  
		        String data = oStack.pop();  
		        if (data.equals(mStack.top())) {  
		            mStack.pop();  
		        }  
		        return data;  
		    }  
		  
		    /**  
		     * 获取栈中最小的元素  
		     * @return 栈中最小的元素  
		     */  
		    public String getMin() {  
		        return mStack.top();  
		    }  
		  
		    public static void main(String[] args) {  
		        AdvancedStack stack = new AdvancedStack();  
		        stack.push(2);  
		        stack.push(6);  
		        stack.push(4);  
		        stack.push(1);  
		        stack.push(5);  
		        System.out.println("The min data in stack is " + stack.getMin());  
		        stack.pop();  
		        System.out.println("The min data in stack is " + stack.getMin());  
		        stack.pop();  
		        System.out.println("The min data in stack is " + stack.getMin());  
		        stack.pop();  
		        System.out.println("The min data in stack is " + stack.getMin());  
		    }  
		}
		</code>
	</pre>
</details>

---

## 时间复杂度
时间复杂度为*O(1)*。

---

## 空间复杂度
空间复杂度为*O(n)*，用于存储最小元素的栈。

---