---
title: "Класс CMenuTearOffManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager class
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 53677bbea54e428e5f080f5c1f73c576abcf99a5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmenutearoffmanager-class"></a>Класс CMenuTearOffManager
Управление перемещаемыми меню. Перемещаемое меню — это меню в строке меню. Пользователь может удалить перемещаемое меню из строки меню, превращая перемещаемое меню в плавающее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Создает объект `CMenuTearOffManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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
 Чтобы использовать перемещаемое меню в приложении, необходимо иметь `CMenuTearOffManager` объекта. В большинстве случаев не создать или инициализировать `CMenuTearOffManager` напрямую. Это выполняется при вызове [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) функции.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как создать и инициализировать `CMenuTearOffManager` путем вызова метода `CWinAppEX::EnableTearOffMenus` метод. Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#12;](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>CMenuTearOffManager::Build  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 Строка, содержащая путь к записи реестра. Приложения параметры хранятся в перемещаемые полос в этой записи реестра.  
  
 [in] `uiTearOffMenuFirst`  
 Первый идентификатор меню перемещаемое меню.  
  
 [in] `uiTearOffMenuLast`  
 Последний идентификатор меню перемещаемое меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов меню из `uiTearOffMenuFirst` для `uiTearOffMenuLast` должна быть непрерывной интервал. Интервал определяет количество перемещаемые меню, появляющихся в то же время в приложении.  
  
##  <a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="parse"></a>CMenuTearOffManager::Parse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `str`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="reset"></a>CMenuTearOffManager::Reset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hmenu`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setinuse"></a>CMenuTearOffManager::SetInUse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)

