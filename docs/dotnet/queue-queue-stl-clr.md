---
title: "queue::queue (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: ["cpp-cli"]
ms.topic: "reference"
f1_keywords: ["cliext::queue::queue"]
dev_langs: ["C++"]
helpviewer_keywords: ["queue member [STL/CLR]"]
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
author: "mikeblome"
ms.author: "mblome"
ms.workload: ["cplusplus", "dotnet"]
---
# queue::queue (STL/CLR)
Constructs a container adapter object.  
  
## Syntax  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### Parameters  
 right  
 Object to copy.  
  
 wrapped  
 Wrapped container to use.  
  
## Remarks  
 The constructor:  
  
 `queue();`  
  
 creates an empty wrapped container. You use it to specify an empty initial controlled sequence.  
  
 The constructor:  
  
 `queue(queue<Value, Container>% right);`  
  
 creates a wrapped container that is a copy of `right.get_container()`. You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the queue object `right`.  
  
 The constructor:  
  
 `queue(queue<Value, Container>^ right);`  
  
 creates a wrapped container that is a copy of `right->get_container()`. You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the queue object `*right`.  
  
 The constructor:  
  
 `explicit queue(container_type wrapped);`  
  
 uses the existing container `wrapped` as the wrapped container. You use it to construct a queue from an existing container.  
  
## Example  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## Requirements  
 **Header:** \<cliext/queue>  
  
 **Namespace:** cliext  
  
## See Also  
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)   
 [queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)