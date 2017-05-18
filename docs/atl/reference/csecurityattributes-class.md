---
title: "Класс CSecurityAttributes | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 24dfba8b6125172cc2d4ff7a32b61da412bfe2be
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="csecurityattributes-class"></a>Класс CSecurityAttributes
Этот класс представляет собой тонкую оболочку для структуры атрибуты безопасности.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityAttributes::Set](#set)|Вызовите этот метод, чтобы задать атрибуты `CSecurityAttributes` объекта.|  
  
## <a name="remarks"></a>Примечания  
 **SECURITY_ATTRIBUTES** структура содержит [дескриптор безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379561) используется для создания объекта и определяет, является ли дескриптор, полученный путем указания эта структура наследуемые.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>CSecurityAttributes::CSecurityAttributes  
 Конструктор.  
  
```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSecurityDescriptor`  
 Ссылка на дескриптор безопасности.  
  
 `bInheritsHandle`  
 Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.  
  
##  <a name="set"></a>CSecurityAttributes::Set  
 Вызовите этот метод, чтобы задать атрибуты `CSecurityAttributes` объекта.  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSecurityDescriptor`  
 Ссылка на дескриптор безопасности.  
  
 `bInheritHandle`  
 Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется конструктором для инициализации `CSecurityAttributes` объекта.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [Дескриптор безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)

