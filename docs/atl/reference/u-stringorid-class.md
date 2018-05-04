---
title: Класс _U_STRINGorID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a601b1c64b28681c13a0b9e8f42156d8820cb4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ustringorid-class"></a>Класс _U_STRINGorID
Этот класс адаптера аргумент позволяет либо имена ресурсов ( `LPCTSTR`s) или идентификаторы ресурсов ( **UINT**s) должны быть переданы функции, не требуя вызывающего объекта, чтобы преобразовать идентификатор в строку с помощью **MAKEINTRESOURCE** макрос.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Конструктор.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Идентификатор ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предназначен для реализации программы-оболочки для API управления ресурса Windows, такими как [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), и [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) функций, которые принимают `LPCTSTR` аргумент, который может быть либо имя ресурса или его идентификатор.  
  
 Этот класс определяет две перегрузки конструктора: одна принимает `LPCTSTR` аргумент, а другой принимает **UINT** аргумент. **UINT** аргумент преобразуется в тип ресурса, совместимые с функциями управления ресурсами Windows с помощью **MAKEINTRESOURCE** макрос и результата, хранимого в едином члена класса, [m_lpstr](#_u_stringorid__m_lpstr). Аргумент `LPCTSTR` конструктор хранится непосредственно, без преобразования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr  
 Класс содержит значение, передаваемое в любой из его конструкторов как общего `LPCTSTR` члена данных.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID  
 **UINT** конструктор Преобразует аргумент в ресурс типа, совместимого с функциями управления ресурсами Windows с помощью **MAKEINTRESOURCE** макрос и результат сохраняется в один класс элемент данных [m_lpstr](#_u_stringorid__m_lpstr).  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор ресурса.  
  
 `lpString`  
 Имя ресурса.  
  
### <a name="remarks"></a>Примечания  
 Аргумент `LPCTSTR` конструктор хранится непосредственно, без преобразования.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
