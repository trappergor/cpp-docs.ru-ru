---
title: "Предупреждение (уровень 4) C4435 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7136cfb61a7452b7e835030216d08f064874df8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4435"></a>Предупреждение компилятора (уровень 4) C4435
"class1": структура объекта в /vd2 изменится из-за виртуального базового класса "class2"  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 В стандартной компиляции параметр/vd1, производный класс не имеет `vtordisp` для указанного виртуального базового.  Если/vd2 или `#pragma vtordisp(2)` , `vtordisp` поле будет присутствовать, изменение макета объекта.  Это может привести к проблемам совместимости с двоичными данными взаимодействующими модули компилируются с различными `vtordisp` параметры.  
  
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