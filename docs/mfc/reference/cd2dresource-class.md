---
title: Класс CD2DResource
ms.date: 03/27/2019
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
ms.openlocfilehash: 5e747eda42e625d0f4cf65859e471933bbb043ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369096"
---
# <a name="cd2dresource-class"></a>Класс CD2DResource

Абстрактный класс, предоставляющий интерфейс для создания и управления d2D-ресурсами, такими как кисти, слои и тексты.

## <a name="syntax"></a>Синтаксис

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DРесурс::CD2DРесурс](#cd2dresource)|Строит объект CD2DResource.|
|[CD2DРесурс:: »CD2DРесурс](#_dtorcd2dresource)|Деструктор Вызывается при уничтожении объекта ресурса D2D.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CD2DРесурс::Создание](#create)|Создает CD2DРесурс.|
|[CD2DРесурс::Dэсстрой](#destroy)|Уничтожает объект CD2DResource.|
|[CD2DРесурс::Действительно](#isvalid)|Проверка достоверности ресурса|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DРесурс::Исавтористия](#isautodestroy)|Проверьте автоматическое уничтожение флага.|
|[CD2DРесурс::Воссоздание](#recreate)|Воссоздает CD2DРесурс.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CD2DРесурс::m_bIsAutoDestroy](#m_bisautodestroy)|Ресурс будет уничтожен владельцем (CRenderTarget)|
|[CD2DРесурс::m_pParentTarget](#m_pparenttarget)|Указатель на родительский CRenderTarget)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>CD2DРесурс:: »CD2DРесурс

Деструктор Вызывается при уничтожении объекта ресурса D2D.

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>CD2DРесурс::CD2DРесурс

Строит объект CD2DResource.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Параметры

*pParentTarget*<br/>
Указатель на цель рендера.

*bAutoDestroy*<br/>
Означает, что объект будет уничтожен владельцем (pParentTarget).

## <a name="cd2dresourcecreate"></a><a name="create"></a>CD2DРесурс::Создание

Создает CD2DРесурс.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a>CD2DРесурс::Dэсстрой

Уничтожает объект CD2DResource.

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2DРесурс::Исавтористия

Проверьте автоматическое уничтожение флага.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если объект будет уничтожен его владельцем; в противном случае FALSE.

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a>CD2DРесурс::Действительно

Проверка достоверности ресурса

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ресурс действителен; в противном случае FALSE.

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a>CD2DРесурс::m_bIsAutoDestroy

Ресурс будет уничтожен владельцем (CRenderTarget)

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a>CD2DРесурс::m_pParentTarget

Указатель на родительский CRenderTarget)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a>CD2DРесурс::Воссоздание

Воссоздает CD2DРесурс.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Параметры

*pRenderTarget*<br/>
Указатель на цель рендера.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
