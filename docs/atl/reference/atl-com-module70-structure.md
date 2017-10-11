---
title: "Структура _ATL_COM_MODULE70 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: a269820c5a0965553989bc57d7c239aa95e527ef
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="atlcommodule70-structure"></a>Структура _ATL_COM_MODULE70
Используемый код с COM в ATL  
  
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
  
## <a name="members"></a>Члены  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_hInstTypeLib`  
 Дескриптор экземпляра, в библиотеку типов для этого модуля.  
  
 **m_ppAutoObjMapFirst**  
 Адрес элемента массива, указывающее начало карты записей объект для этого модуля.  
  
 **m_ppAutoObjMapLast**  
 Адрес элемента массива, указывая на конец объекта карты записей для этого модуля.  
  
 `m_csObjMap`  
 Для сериализации доступ к записям карты объект критической секции. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) определяется как typedef из `_ATL_COM_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Структуры](../../atl/reference/atl-structures.md)






