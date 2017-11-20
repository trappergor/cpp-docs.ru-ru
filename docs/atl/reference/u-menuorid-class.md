---
title: "Класс _U_MENUorID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs: C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ef6563166c658506a33ffa21da285207fbf5275
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Дескриптор для меню.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс адаптера аргумент позволяет либо идентификаторы ( **UINT**s) или дескрипторами меню ( `HMENU`s) должны быть переданы функции, без необходимости явного приведения со стороны вызывающего объекта.  
  
 Этот класс предназначен для реализации программы-оболочки для интерфейса Windows API, особенно [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) и [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции, которые принимают `HMENU` аргумент, который может быть дочерним Идентификатор окна ( **UINT**) вместо дескриптор меню. Например, можно увидеть этот класс используется как параметр [CWindowImpl::Create](cwindowimpl-class.md#create).  

  
 Этот класс определяет две перегрузки конструктора: одна принимает **UINT** аргумент, а другой принимает `HMENU` аргумент. **UINT** аргумент приводится только `HMENU` в конструктор и результата, хранимого в едином члена класса, [m_hMenu](#_u_menuorid__m_hmenu). Аргумент `HMENU` конструктор хранится непосредственно, без преобразования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 Класс содержит значение, передаваемое в любой из его конструкторов как общего `HMENU` члена данных.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT** аргумент приводится только `HMENU` в конструктор и результата, хранимого в едином члена класса, [m_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор дочернего окна элемента.  
  
 `hMenu`  
 Дескриптор меню.  
  
### <a name="remarks"></a>Примечания  
 Аргумент `HMENU` конструктор хранится непосредственно, без преобразования.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
