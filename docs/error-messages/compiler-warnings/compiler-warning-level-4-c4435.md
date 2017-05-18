---
title: "Компилятор C4435 предупреждение (уровень 4) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0d419a4e96ee0716e710b93ce0fa93276ec858aa
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4435"></a>Предупреждение компилятора (уровень 4) C4435
"class1": структура объекта в /vd2 изменится из-за виртуального базового класса "class2"  
  
 Это предупреждение отключено по умолчанию. В разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) подробнее.  
  
 В стандартной компиляции параметр/vd1, производный класс не имеет `vtordisp` для указанного виртуального базового.  Если/vd2 или `#pragma vtordisp(2)` , `vtordisp` поле будет присутствовать, изменение макета объекта.  Это может привести к проблемам совместимости с двоичными данными, если взаимодействующих модули компилируются с различными `vtordisp` параметры.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4435.  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## <a name="see-also"></a>См. также  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/vd (отключение смещений при выполнении конструктора)](../../build/reference/vd-disable-construction-displacements.md)
