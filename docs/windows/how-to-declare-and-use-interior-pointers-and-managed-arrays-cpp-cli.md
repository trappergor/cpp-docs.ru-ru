---
title: 'Практическое: объявление и использование внутренних указателей и управляемых массивов (C + +/ CLI) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45cfc4374b9779a61e3ea97c829317b9d4fe75ba
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016165"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Практическое руководство. Объявление и использование внутренних указателей и управляемых массивов (C++/CLI)
Следующие C + +/ CLI образце показано, как можно объявить и использовать внутренний указатель в массив.  
  
> [!IMPORTANT]
>  Эта функция языка поддерживается параметром компилятора `/clr`, а параметром компилятора `/ZW` не поддерживается.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```cpp  
// interior_ptr_arrays.cpp  
// compile with: /clr  
#define SIZE 10  
  
int main() {  
   // declare the array  
   array<int>^ arr = gcnew array<int>(SIZE);  
  
   // initialize the array  
   for (int i = 0 ; i < SIZE ; i++)  
      arr[i] = i + 1;  
  
   // create an interior pointer into the array  
   interior_ptr<int> ipi = &arr[0];  
  
   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);  
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);  
  
   ipi++;  
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);  
}  
```  
  
```Output  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## <a name="see-also"></a>См. также  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)