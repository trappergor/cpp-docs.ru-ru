---
title: vtordisp | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d0b28c855ab8a6f6da814ee17521a5ad7799993
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42544499"
---
# <a name="vtordisp"></a>vtordisp
**Конкретных C++**  
  
Управляет добавлением скрытого члена смещения конструктора или деструктора vtordisp.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
### <a name="parameters"></a>Параметры  
*push*  
Помещает текущее значение vtordisp внутреннего стека компилятора и устанавливает vtordisp новое *n*.  Если *n* не указан, текущее значение vtordisp не меняется.  
  
*pop*  
Удаляет верхнюю запись из внутреннего стека компилятора и восстанавливает удаленное значение vtordisp.  
  
*n*  
Определяет новое значение vtordisp. Возможные значения: 0, 1 или 2, соответствующие `/vd0`, `/vd1`, и `/vd2` параметры компилятора. Дополнительные сведения см. в разделе [/vd (отключение смещений при выполнении конструктора)](../build/reference/vd-disable-construction-displacements.md).  
  
*on*  
Аналогично параметру `#pragma vtordisp(1)`.  
  
*Отключение*  
Аналогично параметру `#pragma vtordisp(0)`.  
  
## <a name="remarks"></a>Примечания  
 
**Vtordisp** директивы pragma применяется только для кода, использующего виртуальными базовыми классами. Если производный класс переопределяет виртуальную функцию, который наследует от виртуального базового класса, и если конструктор или деструктор для производного класса вызывает эту функцию, используя указатель на виртуальный базовый класс, компилятор может вводить дополнительные скрытые **vtordisp** поля в классы с виртуальными базовыми классами.  
  
**Vtordisp** pragma влияет на структуру классов, которые ей следуют. `/vd0`, `/vd1`, И `/vd2` параметры определяют аналогичное поведение для целых модулей. Указание 0 или *off* подавляет скрытого **vtordisp** членов. Отключить **vtordisp** только при наличии не вероятность того, что конструкторы и деструкторы классов вызывают виртуальные функции объекта, на которые указывают **это** указатель.  
  
Если указать значение 1 или *на*, по умолчанию, то скрытые **vtordisp** членов, когда они необходимы.  
  
Задание 2 скрытые **vtordisp** членов для всех виртуальных базовых классов с виртуальными функциями.  `vtordisp(2)` может потребоваться обеспечить правильное производительность **dynamic_cast** на частично сконструированным объектам. Дополнительные сведения см. в разделе [Предупреждение компилятора (уровень 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
Директива `#pragma vtordisp()` без аргументов восстанавливает исходное значение vtordisp.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)