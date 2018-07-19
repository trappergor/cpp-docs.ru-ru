---
title: Класс _U_STRINGorID | Документация Майкрософт
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
ms.openlocfilehash: 611fecad210b9297b6c7cd16c83dbd0c6c3e41a8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886171"
---
# <a name="ustringorid-class"></a>Класс _U_STRINGorID
Этот класс адаптера аргумент позволяет имена ресурсов (LPCTSTRs) или идентификаторы ресурсов (единицы), должны быть переданы функции, не требуя вызывающий объект, преобразуемый в строку с помощью макроса MAKEINTRESOURCE идентификатор.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Конструктор.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Идентификатор ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предназначен для реализации оболочки для управления ресурсами Windows API, такие как [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), и [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) функций, которые принимают Аргумент LPCTSTR, который может быть либо имя ресурса, либо его идентификатор.  
  
 Этот класс определяет две перегрузки конструктора: один принимает аргумент LPCTSTR, а другой принимает аргумент целое число без знака. Аргумент целое число без знака преобразуется в тип ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса MAKEINTRESOURCE и результата, хранимого в единый данные-член класса, [m_lpstr](#_u_stringorid__m_lpstr). Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr  
 Класс содержит значение, передаваемое в любой из его конструкторов как открытый элемент данных LPCTSTR.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID  
 Конструктор целое число без знака преобразует свой аргумент к типу ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса MAKEINTRESOURCE и результат сохраняется в одном данные-член класса, [m_lpstr](#_u_stringorid__m_lpstr).  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор ресурса.  
  
 *lpString*  
 Имя ресурса.  
  
### <a name="remarks"></a>Примечания  
 Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
