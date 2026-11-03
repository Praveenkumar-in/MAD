ByteXL Coding Lab – 15 Java Programs with Full Questions and Solutions

Platform: ByteXL
Programming Language: Java
Total Questions: 15
Code Format: "public class Main"

---

1. Zigzag Conversion

Problem Statement

A shopping mall displays promotional messages on a digital billboard using a special zigzag layout to attract customers.

Instead of displaying the message in a straight line, the characters are arranged across multiple display rows in a zigzag pattern. After arranging all the characters, the billboard reads the message row by row to generate the final displayed text.

Given a string "message" and an integer "numRows" representing the number of display rows, arrange the characters in a zigzag pattern and return the final message obtained by reading the rows from top to bottom.

Input Format

- The first line contains a string "message".
- The second line contains an integer "numRows".

Output Format

- Print the transformed message after arranging it in the zigzag pattern and reading it row by row.

Constraints

- 1 ≤ message.length ≤ 1000
- Message consists of English letters (uppercase and lowercase), commas and periods.
- 1 ≤ numRows ≤ 1000

Java Solution

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        int n = Integer.parseInt(sc.nextLine().trim());

        if (n == 1 || n >= s.length()) {
            System.out.println(s);
            return;
        }

        StringBuilder[] rows = new StringBuilder[n];

        for (int i = 0; i < n; i++)
            rows[i] = new StringBuilder();

        int row = 0, dir = 1;

        for (char c : s.toCharArray()) {
            rows[row].append(c);

            if (row == 0) dir = 1;
            if (row == n - 1) dir = -1;

            row += dir;
        }

        StringBuilder ans = new StringBuilder();

        for (StringBuilder r : rows)
            ans.append(r);

        System.out.println(ans);
    }
}

Time Complexity: O(n)
Space Complexity: O(n)

---

2. Maximum Number of Vowels in a Substring of Length K

Problem Statement

A monitoring system records a sequence of event codes as a string. Certain event codes are considered priority events, represented by the characters: "a, e, i, o, u".

The system analyzes continuous log segments of fixed length "k" to identify the segment containing the highest number of priority events.

Given a string "logData" and an integer "k", return the maximum number of priority events present in any contiguous segment of length "k".

Input Format

- The first line contains a string "logData".
- The second line contains an integer "k".

Output Format

- Print an integer representing the maximum number of priority events found in any substring of length "k".

Constraints

- 1 ≤ logData.length ≤ 10⁵
- logData consists of lowercase English letters.
- 1 ≤ k ≤ logData.length

Java Solution

import java.util.*;

public class Main {
    static boolean isVowel(char c) {
        return "aeiou".indexOf(c) != -1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String s = sc.nextLine();
        int k = Integer.parseInt(sc.nextLine().trim());

        int count = 0;

        for (int i = 0; i < k; i++) {
            if (isVowel(s.charAt(i)))
                count++;
        }

        int max = count;

        for (int i = k; i < s.length(); i++) {
            if (isVowel(s.charAt(i - k)))
                count--;

            if (isVowel(s.charAt(i)))
                count++;

            max = Math.max(max, count);
        }

        System.out.println(max);
    }
}

Time Complexity: O(n)
Space Complexity: O(1)

---

3. Reverse a Linked List

Problem Statement

A customer support system maintains unresolved service tickets in a linked list. Each ticket contains a unique ticket ID and points to the next ticket waiting to be processed.

Due to a change in the support workflow, the company wants to process the tickets in the reverse order.

Given the head of a singly linked list representing the sequence of ticket IDs, reverse the linked list and return the new head of the reversed ticket sequence.

Input Format

- The first line contains an integer "n", representing the number of tickets.
- The second line contains "n" space-separated integers representing the ticket IDs in the linked list order.

Output Format

- Print the ticket IDs after reversing the linked list.

Constraints

- 0 ≤ n ≤ 5000
- -5000 ≤ ticketIDs[i] ≤ 5000

Java Solution

import java.util.*;

public class Main {
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Node head = null, tail = null;

        for (int i = 0; i < n; i++) {
            Node node = new Node(sc.nextInt());

            if (head == null)
                head = tail = node;
            else {
                tail.next = node;
                tail = node;
            }
        }

        Node prev = null, curr = head;

        while (curr != null) {
            Node next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }

        head = prev;

        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }

        System.out.println();
    }
}

Time Complexity: O(n)
Space Complexity: O(1)

---

4. Factorial Trailing Zeroes

Problem Statement

A warehouse prepares a large shipment by packing "n" boxes. The shipment is assigned a packaging code generated by multiplying all box numbers from 1 to n.

After generating the packaging code, the quality assurance team wants to determine how many zero marks appear consecutively at the end of the code.

Since the packaging code becomes extremely large for higher values of "n", computing the entire product is impractical.

Given an integer "n", representing the number of boxes, determine the number of trailing zeros in the packaging code.

Your solution should be efficient and should not compute the complete product.

Input Format

- A single integer "n" representing the number of boxes.

Output Format

- Return an integer representing the number of trailing zeros in the packaging code.

Constraints

- 0 ≤ n ≤ 10⁴

Java Solution

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int count = 0;

        while (n > 0) {
            n /= 5;
            count += n;
        }

        System.out.println(count);
    }
}

Time Complexity: O(log n)
Space Complexity: O(1)

---

5. Rotate Array to the Right by K Positions

Problem Statement

A warehouse uses a conveyor belt to transport packages in a fixed sequence. At the end of every shift, the conveyor controller rotates the package order to optimize the loading process.

Given an integer array of packages, where each element represents a package ID arranged from left to right on the conveyor belt, and an integer "k" representing the number of right rotations, shift the packages to the right by "k" positions.

The rotation must be performed in-place, using only constant extra space.

Input Format

- The first line contains an integer "n", representing the number of packages.
- The second line contains "n" space-separated integers representing the package IDs.
- The third line contains an integer "k", representing the number of right rotations.

Output Format

- Print the updated arrangement of package IDs after rotating the conveyor belt to the right by "k" positions.

Constraints

- 1 ≤ n ≤ 10⁵
- -2³¹ ≤ packages[i] ≤ 2³¹ - 1

Java Solution

import java.util.*;

public class Main {
    static void reverse(int[] a, int l, int r) {
        while (l < r) {
            int temp = a[l];
            a[l] = a[r];
            a[r] = temp;
            l++;
            r--;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++)
            a[i] = sc.nextInt();

        int k = sc.nextInt();

        if (n > 0) {
            k = ((k % n) + n) % n;

            reverse(a, 0, n - 1);
            reverse(a, 0, k - 1);
            reverse(a, k, n - 1);
        }

        for (int x : a)
            System.out.print(x + " ");

        System.out.println();
    }
}

Time Complexity: O(n)
Space Complexity: O(1)

---

6. Find First and Last Position of Element in Sorted Array

Problem Statement

A manufacturing company stores product batch IDs in sorted order. Multiple products can belong to the same batch, so the same batch ID may appear consecutively in the inventory list.

Given a sorted integer array "batchIds" and an integer "targetBatch", determine the first and last positions where the target batch appears in the inventory.

If the target batch does not exist in the inventory, return "[-1, -1]".

Your solution should run with a time complexity of O(log n).

Input Format

- The first line contains an integer "n", representing the number of batch IDs.
- The second line contains "n" space-separated integers representing the sorted batch IDs.
- The third line contains an integer "targetBatch".

Output Format

- Print two integers representing the first and last positions of the target batch in the array.
- If the target batch is not present, print "-1 -1".

Constraints

- 0 ≤ n ≤ 10⁵
- -10⁹ ≤ batchIds[i] ≤ 10⁹
- The array is sorted in non-decreasing order.
- -10⁹ ≤ targetBatch ≤ 10⁹

Java Solution

import java.util.*;

public class Main {
    static int search(int[] a, int target, boolean first) {
        int l = 0, r = a.length - 1, ans = -1;

        while (l <= r) {
            int mid = l + (r - l) / 2;

            if (a[mid] == target) {
                ans = mid;

                if (first)
                    r = mid - 1;
                else
                    l = mid + 1;
            }
            else if (a[mid] < target)
                l = mid + 1;
            else
                r = mid - 1;
        }

        return ans;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] a = new int[n];

        for (int i = 0; i < n; i++)
            a[i] = sc.nextInt();

        int target = sc.nextInt();

        System.out.println(
            search(a, target, true) + " " +
            search(a, target, false)
        );
    }
}

Time Complexity: O(log n)
Space Complexity: O(1)

---

7. Odd-Even Linked List

Problem Statement

Given the head of a singly linked list, rearrange the list so that all nodes at odd positions come first, followed by all nodes at even positions.

The first node is at position 1. Maintain the relative order of the nodes.

Input Format

- Enter the number of nodes N, followed by N space-separated integers representing the linked list.

Output Format

- Print the rearranged linked list.

Sample Test Case 1

Input

5
1 2 3 4 5

Output

1 3 5 2 4

Java Solution

import java.util.*;

public class Main {
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Node head = null, tail = null;

        for (int i = 0; i < n; i++) {
            Node node = new Node(sc.nextInt());

            if (head == null)
                head = tail = node;
            else {
                tail.next = node;
                tail = node;
            }
        }

        if (head != null) {
            Node odd = head;
            Node even = head.next;
            Node evenHead = even;

            while (even != null && even.next != null) {
                odd.next = even.next;
                odd = odd.next;

                even.next = odd.next;
                even = even.next;
            }

            odd.next = evenHead;
        }

        while (head != null) {
            System.out.print(head.data + " ");
            head = head.next;
        }

        System.out.println();
    }
}

Time Complexity: O(n)
Space Complexity: O(1)

---

8. Evaluate Reverse Polish Notation (RPN)

Problem Statement

You are given an arithmetic expression in Reverse Polish Notation (RPN). Evaluate the expression and return the integer result.

Valid operators are "+", "-", "*", and "/".

Division between two integers should truncate toward zero.

Input Format

- First line: N, the number of tokens.
- Second line: N space-separated tokens. Each token is either an integer or an operator ("+", "-", "*", "/").

Output Format

- Print the integer result.

Sample Test Case 1

Input

5
2 1 + 3 *

Output

9

Java Solution

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Stack<Integer> st = new Stack<>();

        for (int i = 0; i < n; i++) {
            String s = sc.next();

            if (s.equals("+") || s.equals("-") ||
                s.equals("*") || s.equals("/")) {

                int b = st.pop();
                int a = st.pop();

                switch (s) {
                    case "+": st.push(a + b); break;
                    case "-": st.push(a - b); break;
                    case "*": st.push(a * b); break;
                    case "/": st.push(a / b); break;
                }
            } else {
                st.push(Integer.parseInt(s));
            }
        }

        System.out.println(st.pop());
    }
}

Time Complexity: O(n)
Space Complexity: O(n)

---

9. Valid Parentheses

Problem Statement

Given a string "s" containing only the characters "(", ")", "{", "}", "[" and "]", determine if the input string is valid.

A string is valid if:

1. Every opening bracket has a corresponding closing bracket.
2. Brackets are closed in the correct order.
3. Every closing bracket matches the correct opening bracket.

Input Format

- Enter a string containing parentheses/brackets.

Output Format

- Print "true" if the string is valid; otherwise, print "false".

Sample Test Case 1

Input

()

Output

true

Java Solution

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String s = sc.nextLine();
        Stack<Character> st = new Stack<>();

        boolean valid = true;

        for (char c : s.toCharArray()) {
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } else {
                if (st.isEmpty()) {
                    valid = false;
                    break;
                }

                char top = st.pop();

                if ((c == ')' && top != '(') ||
                    (c == '}' && top != '{') ||
                    (c == ']' && top != '[')) {
                    valid = false;
                    break;
                }
            }
        }

        System.out.println(valid && st.isEmpty());
    }
}

Time Complexity: O(n)
Space Complexity: O(n)

---

10. Implement Stack (Push, Pop, Top, Empty)

Problem Statement

A stack follows LIFO (Last In, First Out).

Support the following operations:

- "push(x)" – Add an element.
- "pop()" – Remove the top element.
- "top()" – Return the top element.
- "empty()" – Check if the stack is empty.

If "pop()" or "top()" is performed on an empty stack, print "-1".

Input Format

- The first line contains the number of elements N.
- The second line contains N elements to push into the stack.
- The third line contains the number of pop operations P.

Output Format

Print:

- The elements removed by "pop".
- The top element after the pop operations.
- Whether the stack is empty.

Java Solution

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Stack<Integer> st = new Stack<>();

        for (int i = 0; i < n; i++)
            st.push(sc.nextInt());

        int p = sc.nextInt();

        for (int i = 0; i < p; i++) {
            System.out.print(st.isEmpty() ? -1 : st.pop());
            if (i < p - 1) System.out.print(" ");
        }

        System.out.println();

        System.out.println(st.isEmpty() ? -1 : st.peek());
        System.out.println(st.isEmpty());
    }
}

Time Complexity: O(n + p)
Space Complexity: O(n)

---

11. Path Sum (Binary Tree)

Problem Statement

You are given the root of a binary tree and an integer "targetSum". Determine whether the tree contains a root-to-leaf path such that the sum of all node values along that path equals "targetSum".

A root-to-leaf path starts at the root node and ends at a leaf node. A leaf is a node that has no left or right child.

Return "true" if at least one such path exists. Otherwise, return "false".

Input Format

- The first line contains the binary tree nodes in level-order format. Use "null" to represent a missing node.
- The second line contains an integer "targetSum".

Output Format

- Print "true" if a root-to-leaf path has a sum equal to "targetSum"; otherwise, print "false".

Constraints

- The number of nodes is between 0 and 1000.
- -1000 ≤ Node.val ≤ 1000
- -1000 ≤ targetSum ≤ 1000
- The tree may be empty.

Java Solution

import java.util.*;

public class Main {
    static class Node {
        int val;
        Node left, right;

        Node(int val) {
            this.val = val;
        }
    }

    static boolean hasPathSum(Node root, int sum) {
        if (root == null)
            return false;

        if (root.left == null && root.right == null)
            return sum == root.val;

        return hasPathSum(root.left, sum - root.val) ||
               hasPathSum(root.right, sum - root.val);
    }

    static Node buildTree(String[] a) {
        if (a.length == 0 || a[0].equalsIgnoreCase("null") ||
            a[0].equals("N"))
            return null;

        Node root = new Node(Integer.parseInt(a[0]));
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        int i = 1;

        while (!q.isEmpty() && i < a.length) {
            Node cur = q.poll();

            if (i < a.length && !a[i].equalsIgnoreCase("null")
                && !a[i].equals("N")) {
                cur.left = new Node(Integer.parseInt(a[i]));
                q.add(cur.left);
            }
            i++;

            if (i < a.length && !a[i].equalsIgnoreCase("null")
                && !a[i].equals("N")) {
                cur.right = new Node(Integer.parseInt(a[i]));
                q.add(cur.right);
            }
            i++;
        }

        return root;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] a = sc.nextLine().trim().split("\\s+");
        int target = Integer.parseInt(sc.nextLine().trim());

        Node root = buildTree(a);

        System.out.println(hasPathSum(root, target));
    }
}

Time Complexity: O(n)
Space Complexity: O(n)

---

12. Binary Tree Inorder Traversal

Problem Statement

You are given the root of a binary tree. Write a program to return the inorder traversal of its nodes.

Inorder traversal visits the nodes in the following order:

1. Visit the left subtree.
2. Visit the current node.
3. Visit the right subtree.

Print the values in the order they are visited.

Input Format

- The first line contains the binary tree nodes in level-order format, separated by spaces.
- Use N to represent a missing node.
- An empty tree is represented by N.

Output Format

- Print the inorder traversal as
