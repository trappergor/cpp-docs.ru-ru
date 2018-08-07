---
title: Класс HString | Документация Майкрософт
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
ms.openlocfilehash: 868d0a4e2d84add447c95bfcd9690c8a17850718
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571455"
---
# <a name="hstring-class"></a>Класс HString
Вспомогательный класс для управления жизненным циклом с помощью шаблон RAII HSTRING.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>Примечания  
 Среда выполнения Windows предоставляет доступ к строкам посредством дескрипторов HSTRING. **HString** класс предоставляет удобные функции и операторы для упрощения использования дескрипторов HSTRING. Этот класс может обрабатывать время существования HSTRING, которому он принадлежит через шаблон RAII. 
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор HString::HString](../windows/hstring-hstring-constructor.md)|Инициализирует новый экземпляр класса **HString** класса.|  
|[Деструктор HString::~HString](../windows/hstring-tilde-hstring-destructor.md)|Удаляет текущий экземпляр **HString** класса.|  
  
### <a name="members"></a>Участники  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод HString::Set](../windows/hstring-set-method.md)|Задает значение текущего **HString** объекта с помощью указанной строки расширенных символов или **HString** параметра.|  
|[Метод HString::Attach](../windows/hstring-attach-method.md)|Связывает указанный **HString** объект с текущим **HString** объекта.|  
|[Метод HString::CopyTo](../windows/hstring-copyto-method.md)|Копирует текущий **HString** объект в объект HSTRING.|  
|[Метод HString::Detach](../windows/hstring-detach-method.md)|Отменяет связывание заданных **HString** объект с его базовым значением.|  
|[Метод HString::GetAddressOf](../windows/hstring-getaddressof-method.md)|Извлекает указатель на базовый дескриптор HSTRING.|  
|[Метод HString::Get](../windows/hstring-get-method.md)|Получает значение базового дескриптора HSTRING.|  
|[Метод HString::Release](../windows/hstring-release-method.md)|Удаляет базовое строковое значение и инициализирует текущий **HString** объекта пустое значение.|  
|[Метод HString::MakeReference](../windows/hstring-makereference-method.md)|Создает `HStringReference` объект из указанного строкового параметра.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор HString::Operator=](../windows/hstring-operator-assign-operator.md)|Перемещает значение другого **HString** объект с текущим **HString** объекта.|  
|[Оператор HString::Operator==](../windows/hstring-operator-equality-operator.md)|Указывает, равны ли два параметра.|  
|[Оператор HString::Operator!=](../windows/hstring-operator-inequality-operator.md)|Указывает, действительно ли два параметра не равны.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HString`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)