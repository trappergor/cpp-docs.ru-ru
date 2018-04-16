---
title: Класс FtmBase | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9499a5a30f99e639137532aad1763b434a196809
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="ftmbase-class"></a>FtmBase - класс
Представляет свободнопоточный объект маршаллера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «IMarshal» в подразделе «COM-интерфейсы» раздела «Ссылки COM» в библиотеке MSDN.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор FtmBase::FtmBase](../windows/ftmbase-ftmbase-constructor.md)|Инициализирует новый экземпляр класса FtmBase.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод FtmBase::CreateGlobalInterfaceTable](../windows/ftmbase-createglobalinterfacetable-method.md)|Создает общую таблицу интерфейса (GIT).|  
|[Метод FtmBase::DisconnectObject](../windows/ftmbase-disconnectobject-method.md)|Принудительно освобождает все внешние подключения к объекту. Объект сервера вызывает реализацию объекта до завершения работы этого метода.|  
|[Метод FtmBase::GetMarshalSizeMax](../windows/ftmbase-getmarshalsizemax-method.md)|Верхняя граница получите число байтов, необходимое для маршалинга заданный указатель интерфейса на указанный объект.|  
|[Метод FtmBase::GetUnmarshalClass](../windows/ftmbase-getunmarshalclass-method.md)|Возвращает CLSID, модель COM использует для поиска DLL, содержащая код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания экземпляра неинициализированным прокси-сервера.|  
|[Метод FtmBase::MarshalInterface](../windows/ftmbase-marshalinterface-method.md)|Записывает в поток данные, необходимые для инициализации прокси-объект в некотором процессе клиента.|  
|[Метод FtmBase::ReleaseMarshalData](../windows/ftmbase-releasemarshaldata-method.md)|Удаляет пакет маршалируется данных.|  
|[Метод FtmBase::UnmarshalInterface](../windows/ftmbase-unmarshalinterface-method.md)|Инициализирует только что созданный прокси-сервера и возвращает указатель на интерфейс для прокси-сервера.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных FtmBase::marshaller_](../windows/ftmbase-marshaller-data-member.md)|Хранит ссылку на свободное упаковщик в режиме потока.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `FtmBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)