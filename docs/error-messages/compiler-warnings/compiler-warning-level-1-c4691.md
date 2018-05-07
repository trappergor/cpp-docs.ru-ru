---
title: Предупреждение компилятора предупреждение (уровень 1) C4691 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dccce2468c83dd7d14596c1c26e19bd13ad1a70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4691"></a>Предупреждение компилятора (уровень 1) C4691
«Тип»: ожидался адресуемый тип в сборке без ссылки «файл», тип, определенный в текущей записи преобразования, вместо этого использовать  
  
 Отсутствуют ссылки на файл метаданных, содержащий определение исходного типа, и компилятор использует определение локального типа.  
  
 В случае, когда выполняется перестроение *файл*, пропускаются или отключить с помощью директивы pragma C4691 можно [предупреждение](../../preprocessor/warning.md).  То есть если файл, который вы создаете таким же, как файл, в котором компилятор ожидает найти определение типа, можно игнорировать C4691.  
  
 Тем не менее может возникнуть непредвиденное поведение, если компилятор использует определение, которое не входит в той же сборке, которая указывается в метаданных; Типы CLR относятся к типу не только по имени типа, но также и в сборке.  Тип Z из z.dll сборки является отличается от типа Z из библиотеки y.dll.  
  
## <a name="example"></a>Пример  
 Этот пример содержит определение исходного типа.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>Пример  
 В этом примере ссылка на библиотеку C4691_a.dll и объявляется поле типа Original_Type.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4691.  Обратите внимание, в этом примере содержит определение для Original_Type и не ссылается на библиотеку C4691a.dll.  
  
 Чтобы решить, ссылку на файл метаданных, содержащий определение исходного типа и удалите локальное объявление и определение.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```