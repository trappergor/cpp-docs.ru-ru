---
title: "make_public | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 484462d5a705297f65e82f70fccc23a81eeb719e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="makepublic"></a>make_public
Указывает, что собственный тип должен иметь открытый доступ к сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>Параметры  
 `type` — это имя типа, которому требуется предоставить открытый доступ к сборке.  
  
## <a name="remarks"></a>Примечания  
`make_public` удобно использовать, когда собственный тип, на который нужно сослаться, получен из файла .h, который невозможно изменить. Если требуется использовать собственный тип в сигнатуре открытой функции в типе с открытой видимостью сборки, собственный тип также должен иметь открытый доступ к сборке; в противном случае компилятор выдаст предупреждение.  
  
Ключевое слово `make_public` должно быть определено в глобальной области, и оно действует только с момента его объявления и до конца файла исходного кода.  
  
Собственный тип может быть явно или неявно закрытым; в разделе [видимость типов](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) Дополнительные сведения.  
  
## <a name="example"></a>Пример  
В следующем примере представлено содержимое файла .h, который содержит определения для двух собственных структур.  
  
```cpp  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## <a name="example"></a>Пример  
В следующем примере кода используется файл заголовка и указывается, что, если собственные структуры явно не отметить как открытые с помощью `make_public`, компилятор выдаст предупреждение при попытке использовать собственные структуры в сигнатуре открытой функции в открытом управляемом типе.  
  
```cpp  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## <a name="see-also"></a>См. также  
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)