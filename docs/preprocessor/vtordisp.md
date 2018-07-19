---
title: vtordisp | Документы Microsoft
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
ms.openlocfilehash: 502425728fcd97d2ae8d2efe406dc73370de1272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841776"
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
  
#### <a name="parameters"></a>Параметры  
 `push`  
 Отправляет текущее значение vtordisp во внутренний стек компилятора и устанавливает для vtordisp новое значение `n`.  Если `n` не указано, текущее значение vtordisp не меняется.  
  
 `pop`  
 Удаляет верхнюю запись из внутреннего стека компилятора и восстанавливает удаленное значение vtordisp.  
  
 `n`  
 Определяет новое значение vtordisp. Возможны значения 0, 1 или 2, соответствующие параметрам компилятора /vd0, /vd1 и /vd2. Дополнительные сведения см. в разделе [/vd (отключение смещений при выполнении конструктора)](../build/reference/vd-disable-construction-displacements.md).  
  
 `on`  
 Аналогично параметру `#pragma vtordisp(1)`.  
  
 `off`  
 Аналогично параметру `#pragma vtordisp(0)`.  
  
## <a name="remarks"></a>Примечания  
 Директива #pragma `vtordisp` применяется только к коду, в котором используются виртуальные базовые классы. Если в производном классе переопределена виртуальная функция, которую он унаследовал от виртуального базового класса, и если конструктор или деструктор производного класса вызывает эту функцию при помощи указателя на виртуальный базовый класс, то компилятор может вставлять поля `vtordisp` в классы с виртуальными базовыми классами.  
  
 Директива #pragma `vtordisp` влияет на структуру классов, которые ей следуют. Параметры /vd0, /vd1 и /vd2 определяют аналогичное поведение для целых модулей. Если задано значение `0` или `off`, то добавление скрытых членов `vtordisp` отключается. Директиву #pragma `vtordisp` рекомендуется отключать только в тех случаях, когда конструкторы и деструкторы класса гарантированно не смогут вызывать виртуальные функции объекта, на который указывает указатель `this`.  
  
 Если задано значение по умолчанию `1` или `on`, то скрытые члены `vtordisp` добавляются там, где они необходимы.  
  
 Указание `2` скрытые `vtordisp` члены для виртуальных базовых классов и виртуальных функций.  `vtordisp(2)` может потребоваться для обеспечения правильного производительности `dynamic_cast` на частично сконструированного объекта. Дополнительные сведения см. в разделе [Предупреждение компилятора (уровень 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
 Директива `#pragma vtordisp()` без аргументов восстанавливает исходное значение vtordisp.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)