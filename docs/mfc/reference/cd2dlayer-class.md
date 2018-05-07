---
title: Класс CD2DLayer | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs:
- C++
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 197fc5ecb1b9676dd1ff11327c62950992f6f06d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dlayer-class"></a>Класс CD2DLayer
Программа-оболочка для ID2D1Layer.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Создает объект CD2DLayer.|  
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Деструктор Вызывается при уничтожении объекта D2D слоя.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLayer::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DLayer::CREATE](#create)|Создает CD2DLayer. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLayer::destroy](#destroy)|Уничтожает объект CD2DLayer. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DLayer::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DLayer::Get](#get)|Возвращает интерфейс ID2D1Layer|  
|[CD2DLayer::GetSize](#getsize)|Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселях|  
|[CD2DLayer::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DLayer::operator ID2D1Layer *](#operator_id2d1layer_star)|Возвращает интерфейс ID2D1Layer|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CD2DLayer::m_pLayer](#m_player)|Хранит указатель на объект ID2D1Layer.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DLayer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlayer"></a>  CD2DLayer:: ~ CD2DLayer  
 Деструктор Вызывается при уничтожении объекта D2D слоя.  
  
```  
virtual ~CD2DLayer();
```  
  
##  <a name="attach"></a>  CD2DLayer::Attach  
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1Layer* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
##  <a name="cd2dlayer"></a>  CD2DLayer::CD2DLayer  
 Создает объект CD2DLayer.  
  
```  
CD2DLayer(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="create"></a>  CD2DLayer::CREATE  
 Создает CD2DLayer.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>  CD2DLayer::destroy  
 Уничтожает объект CD2DLayer.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DLayer::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
```  
ID2D1Layer* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>  CD2DLayer::Get  
 Возвращает интерфейс ID2D1Layer  
  
```  
ID2D1Layer* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Layer или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getsize"></a>  CD2DLayer::GetSize  
 Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселях  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий размер целевого объекта отрисовки в аппаратно независимых пикселях  
  
##  <a name="isvalid"></a>  CD2DLayer::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_player"></a>  CD2DLayer::m_pLayer  
 Хранит указатель на объект ID2D1Layer.  
  
```  
ID2D1Layer* m_pLayer;  
```  
  
##  <a name="operator_id2d1layer_star"></a>  CD2DLayer::operator ID2D1Layer *  
 Возвращает интерфейс ID2D1Layer  
  
```  
operator ID2D1Layer* ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Layer или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
