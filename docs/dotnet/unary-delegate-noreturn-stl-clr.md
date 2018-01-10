---
title: "unary_delegate_noreturn (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::unary_delegate_noreturn
dev_langs: C++
helpviewer_keywords: unary_delegate_noreturn function [STL/CLR]
ms.assetid: 3c3fb143-f60f-4e28-a66b-690e3a7b2f9b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 901fbb73305be96a6987928c5cf8c015f85781c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="unarydelegatenoreturn-stlclr"></a>unary_delegate_noreturn (STL/CLR)
Класс genereic описывает один аргумент делегата, который возвращает `void`. Она используется Укажите делегат с точки зрения его типа аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### <a name="parameters"></a>Параметры  
 Arg  
 Тип аргумента.  
  
## <a name="remarks"></a>Примечания  
 Делегат genereic описывает один аргумент функции, которая возвращает `void`.  
  
 Обратите внимание, что для:  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 типы `Fun1` и `Fun2` являются синонимами, а для:  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 они не относятся к одному типу.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
```Output  
hash(a) = 5  
hash(b) = 22  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и функционального >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate (STL/CLR)](../dotnet/unary-delegate-stl-clr.md)