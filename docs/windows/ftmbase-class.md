---
title: Класс FtmBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb3b9ecae955ac78c6139156c3379fcd97511671
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584377"
---
# <a name="ftmbase-class"></a>FtmBase - класс

Представляет свободнопоточный объект маршаллера.

## <a name="syntax"></a>Синтаксис

```cpp
class FtmBase : public Microsoft::WRL::Implements<
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
   Microsoft::WRL::CloakedIid<IMarshal> >;
```

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [класс RuntimeClass](runtimeclass-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор FtmBase::FtmBase](../windows/ftmbase-ftmbase-constructor.md)|Инициализирует новый экземпляр класса **FtmBase** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод FtmBase::CreateGlobalInterfaceTable](../windows/ftmbase-createglobalinterfacetable-method.md)|Создает общую таблицу интерфейса (GIT).|
|[Метод FtmBase::DisconnectObject](../windows/ftmbase-disconnectobject-method.md)|Принудительно освобождает все внешние подключения к объекту. Сервер объекта вызывает реализацию объекта этот метод перед завершением работы системы.|
|[Метод FtmBase::GetMarshalSizeMax](../windows/ftmbase-getmarshalsizemax-method.md)|Получите верхнюю границу на число байтов, необходимая для маршалинга заданный указатель интерфейса на указанный объект.|
|[Метод FtmBase::GetUnmarshalClass](../windows/ftmbase-getunmarshalclass-method.md)|Возвращает идентификатор CLSID, модель COM использует для поиска библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания неинициализированным экземпляром прокси-сервера.|
|[Метод FtmBase::MarshalInterface](../windows/ftmbase-marshalinterface-method.md)|Записывает в поток данные, необходимые для инициализации прокси-объект в какой-либо процесс клиента.|
|[Метод FtmBase::ReleaseMarshalData](../windows/ftmbase-releasemarshaldata-method.md)|Уничтожает пакет маршалированного данных.|
|[Метод FtmBase::UnmarshalInterface](../windows/ftmbase-unmarshalinterface-method.md)|Инициализирует только что созданный прокси-сервер и возвращает указатель интерфейса для этого прокси-сервера.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[Элемент данных FtmBase::marshaller_](../windows/ftmbase-marshaller-data-member.md)|Хранит ссылку на бесплатный упаковщик.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FtmBase`

## <a name="requirements"></a>Требования

**Заголовок:** ftm.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)