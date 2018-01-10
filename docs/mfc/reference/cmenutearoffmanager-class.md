---
title: "Класс CMenuTearOffManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs: C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb1b7acc2f4eb779de49559b5b566e89d518a0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmenutearoffmanager-class"></a>Класс CMenuTearOffManager
Управление перемещаемыми меню. Перемещаемое меню — это меню в строке меню. Пользователь может удалить перемещаемое меню из строки меню, превращая перемещаемое меню в плавающее.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>Синтаксис  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Создает объект `CMenuTearOffManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|Инициализирует `CMenuTearOffManager` объекта.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать перемещаемые меню в приложении, необходимо иметь `CMenuTearOffManager` объекта. В большинстве случаев не будет создать или инициализировать `CMenuTearOffManager` объекта напрямую. Это выполняется при вызове [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) функции.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как создать и инициализировать `CMenuTearOffManager` путем вызова метода `CWinAppEX::EnableTearOffMenus` метод. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 Создает [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) объекта.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не следует создавать `CMenuTearOffManager` вручную. Платформа приложения создает `CMenuTearOffManager` объект при вызове [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).  
  
##  <a name="getregpath"></a>CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="initialize"></a>CMenuTearOffManager::Initialize  
 Инициализирует [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) объекта.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszRegEntry`  
 Строка, содержащая путь к записи реестра. Приложения сохраняет настройки перемещаемые полос в этой записи реестра.  
  
 [in] `uiTearOffMenuFirst`  
 Первый идентификатор меню перемещаемое меню.  
  
 [in] `uiTearOffMenuLast`  
 Последний идентификатор меню перемещаемое меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов, меню из `uiTearOffMenuFirst` для `uiTearOffMenuLast` должен быть непрерывный интервал. Интервал определяет количество перемещаемые меню, появляющееся в то же время в приложении.  
  
##  <a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="parse"></a>CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `str`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="reset"></a>CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hmenu`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setinuse"></a>CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
