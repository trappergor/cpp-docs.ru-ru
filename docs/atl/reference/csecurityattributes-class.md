---
title: Класс CSecurityAttributes | Документация Майкрософт
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
ms.openlocfilehash: 47b0058cba19ac804c2d996052e9a5ec2df68bc5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208952"
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSecurityAttributes::Set](#set)|Вызовите этот метод для задания атрибутов `CSecurityAttributes` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `SECURITY_ATTRIBUTES` Структура содержит [дескриптор безопасности](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) используется для создания объекта и указывает, наследуется ли дескриптор, полученный путем указания этой структуры.  
  
 Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.  
  
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
 *rSecurityDescriptor*  
 Ссылка на дескриптор безопасности.  
  
 *bInheritsHandle*  
 Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.  
  
##  <a name="set"></a>  CSecurityAttributes::Set  
 Вызовите этот метод для задания атрибутов `CSecurityAttributes` объекта.  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *rSecurityDescriptor*  
 Ссылка на дескриптор безопасности.  
  
 *bInheritHandle*  
 Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется конструктором для инициализации `CSecurityAttributes` объекта.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [Дескриптор безопасности](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
