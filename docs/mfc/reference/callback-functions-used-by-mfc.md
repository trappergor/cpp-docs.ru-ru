---
title: Функции обратного вызова, используемые MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce96d90506176812ffb70b580c9d95a38c65fa19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="callback-functions-used-by-mfc"></a>Функции обратного вызова, используемые MFC
В библиотеке Microsoft Foundation Class отображаются три функции обратного вызова. Эти функции обратного вызова передаются [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), и [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Обратите внимание, что все функции обратного вызова должен перехватываются исключения MFC перед возвратом Windows, так как исключения не может вызываться через границы обратного вызова. Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  

|Имя||  
|----------|-----------------|  
|[Функция обратного вызова для CDC::EnumObjects](#enum_objects)||  
|[Функция обратного вызова для CDC::GrayString](#graystring)||
|[Функция обратного вызова для CDC::SetAbortProc](#setabortproc)|| 

## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h 

## <a name="enum_objects"></a> Функция обратного вызова для CDC::EnumObjects
*ObjectFunc* имя — это имя функции, предоставляемой приложением.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLogObject*  
 Указывает на [LOGPEN](../../mfc/reference/logpen-structure.md) или [LOGBRUSH](../../mfc/reference/logbrush-structure.md) структуру данных, содержащую сведения о логических атрибутов объекта.  
  
 `lpData`  
 Указывает на данные, предоставляемую приложением, передаваемый `EnumObjects` функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция обратного вызова возвращает `int`. Это возвращаемое значение определяется пользователем. Если функция обратного вызова возвращает значение 0, `EnumObjects` останавливает раньше перечисления.  
  
### <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать.  
  
## <a name="graystring"></a>  Функция обратного вызова для CDC::GrayString
*OutputFunc* — это имя функции обратного вызова, предоставляемую приложением.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `hDC`  
 Определяет контекст устройства памяти с растровым изображением, по меньшей мере ширины и высоты, определяемое `nWidth` и `nHeight` для `GrayString`.  
  
 `lpData`  
 Указывает на строку символов, которую необходимо нарисовать.  
  
 `nCount`  
 Указывает число символов для вывода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение функции обратного вызова должен быть **TRUE** в случае успеха; в противном случае это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Функция обратного вызова (*OutputFunc*) необходимо нарисовать изображение относительно координат (0,0) вместо (*x*, *y*).  

## <a name="setabortproc"></a>  Функция обратного вызова для CDC::SetAbortProc
Имя *AbortFunc* — это имя функции, предоставляемой приложением.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>Параметры  
 *hPr*  
 Определяет контекст устройства.  
  
 `code`  
 Указывает, является ли ошибка. Оно равно 0, если ошибки не произошло. Это **SP_OUTOFDISK** Если диспетчера печати находится недостаточно места на диске и места на диске скоро станет доступен, если приложение ожидает. Если `code` — **SP_OUTOFDISK**, приложения не требуется прервать задание печати. Если нет, она должна возвращать для диспетчера печати путем вызова **PeekMessage** или **GetMessage** функции Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функции обработчика прерывания возвращается ненулевое значение, если задание печати будет продолжаться и 0, если его отмены.  
  
### <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать, как описано в подразделе "Примечания" [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md) [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects) [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc) [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)

