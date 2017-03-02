---
title: "Класс CD2DPathGeometry | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DPathGeometry
- CD2DPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry class
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1c1158e55bf12d44f34896dd6752c9b8706db636
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpathgeometry-class"></a>Класс CD2DPathGeometry
Программа-оболочка для ID2D1PathGeometry.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Создает объект CD2DPathGeometry.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DPathGeometry::CREATE](#create)|Создает CD2DPathGeometry. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DPathGeometry::destroy](#destroy)|Уничтожает объект CD2DPathGeometry. (Переопределяет [CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|  
|[CD2DPathGeometry::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Получает число фигур в по геометрическому пути.|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Получает число сегментов геометрическому пути.|  
|[CD2DPathGeometry::Open](#open)|Получает геометрию приемника, который используется для заполнения по геометрическому пути с фигуры и сегменты.|  
|[CD2DPathGeometry::Stream](#stream)|Копирует содержимое по геометрическому пути указанного ID2D1GeometrySink.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Указатель на ID2D1PathGeometry.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-nameattacha--cd2dpathgeometryattach"></a><a name="attach"></a>CD2DPathGeometry::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="a-namecd2dpathgeometrya--cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a>CD2DPathGeometry::CD2DPathGeometry  
 Создает объект CD2DPathGeometry.  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dpathgeometrycreate"></a><a name="create"></a>CD2DPathGeometry::CREATE  
 Создает CD2DPathGeometry.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namedestroya--cd2dpathgeometrydestroy"></a><a name="destroy"></a>CD2DPathGeometry::destroy  
 Уничтожает объект CD2DPathGeometry.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dpathgeometrydetach"></a><a name="detach"></a>CD2DPathGeometry::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="a-namegetfigurecounta--cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount  
 Получает число фигур в по геометрическому пути.  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число фигур геометрическому пути.  
  
##  <a name="a-namegetsegmentcounta--cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount  
 Получает число сегментов геометрическому пути.  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число сегментов геометрическому пути.  
  
##  <a name="a-namemppathgeometrya--cd2dpathgeometrymppathgeometry"></a><a name="m_ppathgeometry"></a>CD2DPathGeometry::m_pPathGeometry  
 Указатель на ID2D1PathGeometry.  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="a-nameopena--cd2dpathgeometryopen"></a><a name="open"></a>CD2DPathGeometry::Open  
 Получает геометрию приемника, который используется для заполнения по геометрическому пути с фигуры и сегменты.  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на ID2D1GeometrySink, используемый для заполнения по геометрическому пути с фигуры и сегменты.  
  
##  <a name="a-namestreama--cd2dpathgeometrystream"></a><a name="stream"></a>CD2DPathGeometry::Stream  
 Копирует содержимое по геометрическому пути указанного ID2D1GeometrySink.  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>Параметры  
 `geometrySink`  
 Приемник, в который будет скопировано содержимое по геометрическому пути. Изменив этот приемник не изменяет содержимое этой геометрическому пути.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

