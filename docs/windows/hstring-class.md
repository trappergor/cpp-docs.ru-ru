---
title: Класс HString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8544a78fdbdab19f44081853f5f5878f980cec01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879376"
---
# <a name="hstring-class"></a>Класс HString
Вспомогательный класс для управления временем жизни HSTRING, используя шаблон RAII.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>Примечания  
 Среда выполнения Windows предоставляет доступ к строки через дескрипторов HSTRING. Класс HString предоставляет удобных функций и операторов, чтобы упростить использование дескрипторов HSTRING. Этот класс может обрабатывать HSTRING, он владеет через шаблон RAII времени существования. 
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор HString::HString](../windows/hstring-hstring-constructor.md)|Инициализирует новый экземпляр класса HString.|  
|[Деструктор HString::~HString](../windows/hstring-tilde-hstring-destructor.md)|Удаляет текущий экземпляр класса HString.|  
  
### <a name="members"></a>Участники  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод HString::Set](../windows/hstring-set-method.md)|Задает значение текущий объект HString указанную строку расширенных символов или параметра HString.|  
|[Метод HString::Attach](../windows/hstring-attach-method.md)|Связывает указанный объект HString с текущий объект HString.|  
|[Метод HString::CopyTo](../windows/hstring-copyto-method.md)|Копирует текущий HString объект к объекту HSTRING.|  
|[Метод HString::Detach](../windows/hstring-detach-method.md)|Отсоединяет указанный объект HString из его базовое значение.|  
|[Метод HString::GetAddressOf](../windows/hstring-getaddressof-method.md)|Извлекает указатель на базовый дескриптор HSTRING.|  
|[Метод HString::Get](../windows/hstring-get-method.md)|Возвращает значение базового дескриптора HSTRING.|  
|[Метод HString::Release](../windows/hstring-release-method.md)|Удаляет значение исходной строки и инициализирует текущий объект HString пустым.|  
|[Метод HString::MakeReference](../windows/hstring-makereference-method.md)|Создает объект HStringReference из указанного строкового параметра.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор HString::Operator=](../windows/hstring-operator-assign-operator.md)|Перемещает текущий объект HString значение другого объекта HString.|  
|[Оператор HString::Operator==](../windows/hstring-operator-equality-operator.md)|Указывает, равны ли два параметра.|  
|[Оператор HString::Operator!=](../windows/hstring-operator-inequality-operator.md)|Указывает, равны ли два параметра.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HString`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)