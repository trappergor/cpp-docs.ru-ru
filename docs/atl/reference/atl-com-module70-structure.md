---
title: Структура _ATL_COM_MODULE70 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a3140a0013d284b9145029575418054af22c65e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883717"
---
# <a name="atlcommodule70-structure"></a>Структура _ATL_COM_MODULE70
Используемый код, связанный с COM в ATL  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>Участники  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_hInstTypeLib`  
 Дескриптор экземпляра, в библиотеку типов для этого модуля.  
  
 `m_ppAutoObjMapFirst`  
 Адрес элемента массива, который задает начало карты записей объект для этого модуля.  
  
 `m_ppAutoObjMapLast`  
 Адрес элемента массива, указывающий на конец записи сопоставления объекта для этого модуля.  
  
 `m_csObjMap`  
 Критический раздел для сериализации доступа к записям объекта карты. Используется системой ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) определяется как typedef типа _ATL_COM_MODULE70.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../../atl/reference/atl-classes.md)





