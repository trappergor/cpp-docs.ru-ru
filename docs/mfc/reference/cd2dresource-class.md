---
title: Класс CD2DResource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eed5b60954d05094db610a233968c9c7dd83c704
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dresource-class"></a>Класс CD2DResource
Абстрактный класс, который предоставляет интерфейс для создания и управления ресурсы D2D, например кистей, слоев и текстов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|Создает объект CD2DResource.|  
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|Деструктор Вызывается при уничтожении объекта D2D ресурсов.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DResource::CREATE](#create)|Создает CD2DResource.|  
|[CD2DResource::destroy](#destroy)|Уничтожает объект CD2DResource.|  
|[CD2DResource::IsValid](#isvalid)|Проверяет допустимость ресурсов|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Проверка автоматического уничтожить флаг.|  
|[CD2DResource::ReCreate](#recreate)|Повторно создает CD2DResource.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Ресурс будет destoyed владельцем (CRenderTarget)|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|Указатель на родительский CRenderTarget)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dresource"></a>  CD2DResource:: ~ CD2DResource  
 Деструктор Вызывается при уничтожении объекта D2D ресурсов.  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource  
 Создает объект CD2DResource.  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="create"></a>  CD2DResource::CREATE  
 Создает CD2DResource.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>  CD2DResource::destroy  
 Уничтожает объект CD2DResource.  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy  
 Проверка автоматического уничтожить флаг.  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если объект будет уничтожен его владельцу. в противном случае — значение FALSE.  
  
##  <a name="isvalid"></a>  CD2DResource::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy  
 Ресурс будет destoyed владельцем (CRenderTarget)  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget  
 Указатель на родительский CRenderTarget)  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="recreate"></a>  CD2DResource::ReCreate  
 Повторно создает CD2DResource.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
