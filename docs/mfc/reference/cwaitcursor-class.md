---
title: "Класс CWaitCursor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- cursors, wait cursor
- CWaitCursor class
- wait cursors
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f72598c356add5d891b013f1fd7b87665c5a6c63
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cwaitcursor-class"></a>Класс CWaitCursor
Предоставляет односторонний способ отображения курсора ожидания (который обычно отображается как песочные часы) при выполнении длительной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Создает `CWaitCursor` объекта и отображает курсор ожидания.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|Восстанавливает курсор ожидания будет после изменения.|  
  
## <a name="remarks"></a>Примечания  
 `CWaitCursor`не имеет базового класса.  
  
 Хороший Windows методик программирования требуют отображения курсора ожидания, каждый раз, когда вы выполняете операцию, занимающую длительное время.  
  
 Чтобы отобразить курсор ожидания, достаточно определить `CWaitCursor` переменной перед кодом, который выполняет длительных операций. Конструктор объекта автоматически вызывает курсор ожидания для отображения.  
  
 Когда объект выходит за пределы области (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор для предыдущего курсора. Другими словами объект выполняет необходимые очистки автоматически.  
  
> [!NOTE]
>  Из-за их конструкторы и деструкторы работы `CWaitCursor` объектов всегда были объявлены как локальные переменные, они никогда не объявляются как глобальные переменные, ни их выделения с **новый**.  
  
 При выполнении операции, что может привести к курсор, изменить, например, отображение окна сообщения или диалоговое окно, вызов [восстановить](#restore) функции-члена для восстановления курсор ожидания. Допустимо вызывать **восстановить** даже если курсор ожидания в настоящий момент отображается.  
  
 Другой способ отображения курсора ожидания является использование сочетание [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)и, возможно, [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Однако `CWaitCursor` проще в использовании, так как не нужно установить курсор на предыдущем курсор после завершения с длительной операции.  
  
> [!NOTE]
>  Задает MFC и восстанавливает курсора с помощью [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) виртуальной функции. Можно переопределить эту функцию, чтобы обеспечить пользовательское поведение.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CWaitCursor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#62;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Чтобы отобразить курсор ожидания, просто объявите `CWaitCursor` объекта перед кодом, который выполняет длительных операций.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор автоматически вызывает курсор ожидания для отображения.  
  
 Когда объект выходит за пределы области (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор для предыдущего курсора. Другими словами объект выполняет необходимые очистки автоматически.  
  
 Можно воспользоваться преимуществами тот факт, что деструктор вызывается в конце блока (что может быть до конца функции) чтобы сделать активным курсор ожидания в части функции. Во втором примере ниже показан этот метод.  
  
> [!NOTE]
>  Из-за их конструкторы и деструкторы работы `CWaitCursor` объектов всегда были объявлены как локальные переменные, они никогда не объявляются как глобальные переменные, а также их выделения с **новый**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#63;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 Чтобы восстановить курсор ожидания, эта функция вызывается после выполнения операции, например при отображении окно сообщения или диалоговое окно, которое может изменить курсор ожидания для другого курсора.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать **восстановить** даже если курсор ожидания в настоящий момент отображается.  
  
 Если необходимо восстановить курсор ожидания в функции, отличные от той, в которой `CWaitCursor` объявлен объект, можно вызвать [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#64;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [Как изменить курсор мыши в приложении классов Microsoft Foundation I:](http://go.microsoft.com/fwlink/linkid=128044)




