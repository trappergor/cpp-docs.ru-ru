---
title: Пространство имен Microsoft::WRL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
dev_langs:
- C++
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37d4d5391da4dfb6e25754eb1350224acb97e972
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="microsoftwrl-namespace"></a>Пространство имен Microsoft::WRL
Определяет основные типы, составляющие библиотека шаблонов C++ среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="typedefs"></a>Определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс ActivationFactory](../windows/activationfactory-class.md)|Позволяет одному или нескольким классам быть активированными средой выполнения Windows.|  
|[Класс AsyncBase](../windows/asyncbase-class.md)|Реализует асинхронный конечный автомат среды выполнения Windows.|  
|[Класс ClassFactory](../windows/classfactory-class.md)|Реализует базовую функциональность интерфейса `IClassFactory`.|  
|[Класс ComPtr](../windows/comptr-class.md)|Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.|  
|[Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)|Класс шаблона, используемый для типов аргументов событий для задержек.|  
|[Класс EventSource](../windows/eventsource-class.md)|Представляет событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий.|  
|[Класс FtmBase](../windows/ftmbase-class.md)|Представляет свободнопоточный объект маршаллера.|  
|[Класс Module](../windows/module-class.md)|Представляет коллекцию связанных объектов.|  
|[Класс RuntimeClass](../windows/runtimeclass-class.md)|Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.|  
|[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)|Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.|  
|[Класс SimpleClassFactory](../windows/simpleclassfactory-class.md)|Предоставляет основной механизм для создания базового класса.|  
|[Класс WeakRef](../windows/weakref-class.md)|Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)|Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.|  
|[Структура CloakedIid](../windows/cloakediid-structure.md)|Указывает шаблонам RuntimeClass, Implements и ChainInterfaces, что заданный интерфейс недоступен в списке IID.|  
|[Структура Implements](../windows/implements-structure.md)|Реализует QueryInterface и GetIid для указанных интерфейсов.|  
|[Структура MixIn](../windows/mixin-structure.md)|Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.|  
|[Структура RuntimeClassFlags](../windows/runtimeclassflags-structure.md)|Содержит тип экземпляра класса [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Перечисления  
  
|name|Описание|  
|----------|-----------------|  
|[Перечисление AsyncResultType](../windows/asyncresulttype-enumeration.md)|Указывает тип результата, возвращаемого методом GetResults().|  
|[Перечисление ModuleType](../windows/moduletype-enumeration.md)|Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.|  
|[Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md)|Указывает тип [RuntimeClass](../windows/runtimeclass-class.md) экземпляр, который поддерживается.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция AsWeak](../windows/asweak-function.md)|Извлекает слабую ссылку на определенный экземпляр.|  
|[Функция обратного вызова](../windows/callback-function-windows-runtime-cpp-template-library.md)|Создает объект, функция-член которого является методом обратного вызова.|  
|[Функция CreateActivationFactory](../windows/createactivationfactory-function.md)|Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.|  
|[Функция CreateClassFactory](../windows/createclassfactory-function.md)|Создает фабрику, которая создает экземпляры указанного класса.|  
|[Функция Make](../windows/make-function.md)|Инициализирует указанный класс среды выполнения Windows.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)