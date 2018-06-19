---
title: deque::Resize (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::resize
dev_langs:
- C++
helpviewer_keywords:
- resize member [STL/CLR]
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0d7e68fa1a58e70d4b414f81ca826e632c8706bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108885"
---
# <a name="dequeresize-stlclr"></a>deque::resize (STL/CLR)
Изменяет количество элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Параметры  
 new_size  
 Новый размер управляемой последовательности.  
  
 функция Val  
 Значение элемента-заполнителя.  
  
## <a name="remarks"></a>Примечания  
 Убедитесь, что функции-члены обоих [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `()` исходя из возвращает `new_size`. Если это вынуждает сделать более длинной управляемую последовательность, первая функция-член добавляет элементы со значением `value_type()`, тогда как вторая функция-член добавляет элементы со значением `val`. Чтобы сделать более короткие управляемой последовательности, обе функции-члены фактически удалить последний элемент [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() -` `new_size` раз. Используется, чтобы обеспечить размер управляемой последовательности `new_size`, trimming или заполнения текущего управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/deque >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::Clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)   
 [deque::Erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)