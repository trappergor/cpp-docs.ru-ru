---
title: Класс HStringReference | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90e94471fe114eafec91a19ddad5d47ce39a8de7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879559"
---
# <a name="hstringreference-class"></a>Класс HStringReference
Представляет HSTRING, созданной из существующей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>Примечания  
 Время существования резервный буфер в новый HSTRING не управляется средой выполнения Windows. Вызывающий объект выделяет строку источника, чтобы избежать выделения кучи и избежать утечки памяти в стеке. Кроме того вызывающий объект должен убедиться, исходная строка остается неизменным в течение времени существования вложенного HSTRING. Дополнительные сведения см. в разделе [WindowsCreateStringReference функция](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор HStringReference::HStringReference](../windows/hstringreference-hstringreference-constructor.md)|Инициализирует новый экземпляр класса HStringReference.|  
  
### <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|[Метод HStringReference::CopyTo](../windows/hstringreference-copyto-method.md)|Копирует текущий HStringReference объект к объекту HSTRING.|  
|[Метод HStringReference::Get](../windows/hstringreference-get-method.md)|Возвращает значение базового дескриптора HSTRING.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор HStringReference::Operator=](../windows/hstringreference-operator-assign-operator.md)|Значение другой объект HStringReference перемещается в текущий объект HStringReference.|  
|[Оператор HStringReference::Operator==](../windows/hstringreference-operator-equality-operator.md)|Указывает, равны ли два параметра.|  
|[Оператор HStringReference::Operator!=](../windows/hstringreference-operator-inequality-operator.md)|Указывает, равны ли два параметра.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HStringReference`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)