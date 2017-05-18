---
title: "Функции обратного вызова, используемые MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
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
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 08c6f547c95adb4c6794ec71259888d390e42e92
ms.contentlocale: ru-ru
ms.lasthandoff: 03/06/2017

---
# <a name="callback-functions-used-by-mfc"></a>Функции обратного вызова, используемые MFC
Три функции обратного вызова отображаются в библиотеке Microsoft Foundation Class. Эти функции обратного вызова передаются [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), и [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Обратите внимание, что все функции обратного вызова необходимо перехват исключений MFC перед возвратом Windows, так как не удается исключения через границы обратного вызова. Дополнительные сведения об исключениях см. в статье [исключения](../../mfc/exception-handling-in-mfc.md).  

|Имя||  
|----------|-----------------|  
|[Функция обратного вызова для CDC::EnumObjects](#enum_objects)||  
|[Функция обратного вызова для CDC::GrayString](#graystring)||
|[Функция обратного вызова для CDC::SetAbortProc](#setabortproc)|| 

## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h 

## <a name="enum_objects"></a>Функция обратного вызова для CDC::EnumObjects
*ObjectFunc* имя — это имя функции, предоставляемой приложением.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszLogObject*  
 Указывает [LOGPEN](../../mfc/reference/logpen-structure.md) или [LOGBRUSH](../../mfc/reference/logbrush-structure.md) структуру данных, содержащую сведения о логических атрибутов объекта.  
  
 `lpData`  
 Указывает на основе предоставленных приложением данных, передаваемый `EnumObjects` функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция обратного вызова возвращает `int`. Это возвращаемое значение определяется пользователем. Если функция обратного вызова возвращает 0, `EnumObjects` останавливает перечисления раньше.  
  
### <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать.  
  
## <a name="graystring"></a>Функция обратного вызова для CDC::GrayString
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
 Определяет контекст устройства памяти с растровым изображением, по меньшей мере ширину и высоту, определяемой `nWidth` и `nHeight` в `GrayString`.  
  
 `lpData`  
 Указывает на строку символов, которую необходимо нарисовать.  
  
 `nCount`  
 Указывает число символов для вывода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение функции обратного вызова должен быть **TRUE** в случае успеха; в противном случае это **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Функция обратного вызова (*OutputFunc*) должен рисования изображения относительно координат (0,0) вместо (*x*, *y*).  

## <a name="setabortproc"></a>Функция обратного вызова для CDC::SetAbortProc
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
 Указывает, является ли ошибка. Оно равно 0, если ошибки не произошло. Это **SP_OUTOFDISK** Если диспетчер печати находится свободного дискового пространства и больше места на диске станет доступной, если приложение ожидает. Если `code` — **SP_OUTOFDISK**, приложения не требуется прервать задание печати. Если нет, он должен уступить диспетчера печати путем вызова **PeekMessage** или **GetMessage** функции Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение функции обработчика прерывания ненулевым, если задание печати для продолжения и 0 после отмены.  
  
### <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать, как описано в подразделе "Примечания" [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](structures-styles-callbacks-and-message-maps.md)
 [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)
 [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)
 [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)


