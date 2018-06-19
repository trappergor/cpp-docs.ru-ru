---
title: Ошибка компилятора C3813 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e947b281c90c4d2ace83971f1de972c29bde72ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273111"
---
# <a name="compiler-error-c3813"></a>Ошибка компилятора C3813
объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT  
  
Объект [свойство](../../dotnet/how-to-use-properties-in-cpp-cli.md) можно объявлять только в пределах управляемого типа или среды выполнения Windows тип. Собственные типы не поддерживают ключевое слово `property`.  
  
## <a name="example"></a>Пример  
В следующем примере показано возникновение ошибки C3813 и приводятся сведения по ее устранению.  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```