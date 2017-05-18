---
title: "Класс _U_MENUorID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f7c0a5c34c4e103f830a029f58cdfa00dcb58a32
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="umenuorid-class"></a>Класс _U_MENUorID
Этот класс предоставляет оболочки для **CreateWindow** и **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Конструктор.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Дескриптор меню.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс адаптера аргумент позволяет либо идентификаторы ( **UINT**s) или маркеры меню ( `HMENU`s) должны быть переданы функции, без необходимости явного приведения со стороны вызывающего объекта.  
  
 Этот класс предназначен для реализации программы-оболочки для Windows API, особенно [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) и [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции, которые принимают `HMENU` аргумент, который может быть идентификатором дочернего окна ( **UINT**) вместо дескриптор меню. Например, можно увидеть этот класс используется в качестве параметра [CWindowImpl::Create](cwindowimpl-class.md#create).  

  
 Этот класс определяет две перегрузки конструктора: одна принимает **UINT** аргумент, а другой принимает `HMENU` аргумент. **UINT** аргумент приводится только `HMENU` в конструктор и результат, хранящийся в едином члена класса, [m_hMenu](#_u_menuorid__m_hmenu). Аргумент `HMENU` конструктор сохраняется непосредственно, без преобразования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 Класс содержит значение, передаваемое в любой из его конструкторов как открытый `HMENU` члена данных.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT** аргумент приводится только `HMENU` в конструктор и результат, хранящийся в едином члена класса, [m_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор дочернего окна.  
  
 `hMenu`  
 Дескриптор меню.  
  
### <a name="remarks"></a>Примечания  
 Аргумент `HMENU` конструктор сохраняется непосредственно, без преобразования.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

