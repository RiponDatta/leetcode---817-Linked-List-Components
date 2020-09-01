# leetcode 817 - Linked List Components

## C#
```C#
public static int NumComponents(ListNode head, int[] G)
{
    // G has unique integer values, hence we can simply use constructor function to assign the G in the hashset.
    var hs = new HashSet<int>(G);

    int maxConnected = 0;
    while(head != null)
    {
        if (hs.Contains(head.val) && (head.next == null || !hs.Contains(head.next.val)))
            maxConnected++;
                
        head = head.next;
    }
    return maxConnected;
}
```

#### Complexity Analysis
* Time Complexity: O(N + G.length), N is the length of the list
* Space Complexity: O(G.length)
