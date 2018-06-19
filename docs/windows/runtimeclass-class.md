---
title: Класс RuntimeClass | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26c3542f5bea21d1b705cd3253e6828ff73677df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889011"
---
# <a name="runtimeclass-class"></a>Класс RuntimeClass
Представляет WinRT или COM-класс, наследующий указанных интерфейсов и предоставляет указанную среду выполнения Windows, классических COM и поддержку слабых ссылок.  
  
Этот класс предоставляет стандартный реализации классов WinRT и COM, при условии реализации `QueryInterface`, `AddRef`, `Release` и др., управляет счетчиком ссылок модуля и включает поддержку фабрику класса для предоставления Активируемый объекты.
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
#### <a name="parameters"></a>Параметры  
 `classFlags`  
Необязательный параметр ". Сочетание одного или нескольких [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значений перечисления. `__WRL_CONFIGURATION_LEGACY__` Макрос можно определить таким образом, чтобы изменить значение по умолчанию classFlags для всех классов среды выполнения в проекте. Если определено, не являются гибкими по умолчанию экземпляра RuntimeClass. Если не определен, RuntimeClass экземпляры являются гибкими по умолчанию. Чтобы избежать неоднозначности всегда указывать Microsoft::WRL::FtmBase в `TInterfaces` или RuntimeClassType::InhibitFtmBase. Обратите внимание, если InhibitFtmBase и FtmBase, как использовать объект будет agile.
 
 `TInterfaces`  
Список интерфейсов, реализуемых объектом после IUnknown, IInspectable или других интерфейсов, которые управляются [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Он также может содержать другие классы, производные от особенно Microsoft::WRL::FtmBase для создания объекта agile и приводит к его реализации интерфейса IMarshal.
  
## <a name="members"></a>Участники  
`RuntimeClassInitialize` Функция, которая инициализирует объект, если функция MakeAndInitialize шаблон используется для создания объекта. Возвращает значение S_OK, если объект успешно инициализирован, или код ошибки COM. Если не удалось выполнить инициализацию. Код ошибки COM. распространяется в виде MakeAndInitialize возвращаемое значение. Обратите внимание, что метод RuntimeClassInitialize не вызывается, если функция Создание шаблона используется для создания объекта.

### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор RuntimeClass::RuntimeClass](../windows/runtimeclass-runtimeclass-constructor.md)|Инициализирует текущий экземпляр класса RuntimeClass.|  
|[Деструктор RuntimeClass::~RuntimeClass](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Деинициализирует текущий экземпляр класса RuntimeClass.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
Это реализации.
  
## <a name="requirements"></a>Требования  
**Заголовок:** implements.h  
  
**Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
