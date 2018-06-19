---
title: Класс CSecurityAttributes | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03bda174fb85fa6857e22b851b93bcf1b3192716
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357510"
---
# <a name="csecurityattributes-class"></a>Класс CSecurityAttributes
Этот класс является тонкой оболочкой для структуры атрибуты безопасности.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityAttributes::Set](#set)|Этот метод вызывается для установки атрибутов `CSecurityAttributes` объекта.|  
  
## <a name="remarks"></a>Примечания  
 **SECURITY_ATTRIBUTES** структура содержит [дескриптор безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379561) используется для создания объекта и указывает, является ли дескриптор, полученные путем указания эта структура наследуемые.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes  
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
  
##  <a name="set"></a>  CSecurityAttributes::Set  
 Этот метод вызывается для установки атрибутов `CSecurityAttributes` объекта.  
  
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
