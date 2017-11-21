---
title: "Класс CWaitCursor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs: C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b4e30b024b6a83a7ea2069386cff3166ce518faa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CWaitCursor::Restore](#restore)|Восстанавливает курсор ожидания после он изменяется.|  
  
## <a name="remarks"></a>Примечания  
 `CWaitCursor`не имеет базового класса.  
  
 Хороший Windows методик программирования требуют отображения курсора ожидания, при каждом выполнении операцию, занимающую длительное время.  
  
 Для отображения курсора ожидания, просто определить `CWaitCursor` переменной перед кодом, который выполняет длительных операций. В конструктор объекта автоматически вынуждает курсор ожидания для отображения.  
  
 Когда объект выходит за пределы области (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор к предыдущей курсора. Другими словами объект выполняет необходимые очистки автоматически.  
  
> [!NOTE]
>  Из-за их конструкторы и деструкторы работе `CWaitCursor` объекты всегда объявляются как локальные переменные, они никогда не описаны как глобальные переменные и не выделяются они с **новый**.  
  
 При выполнении операции, что может привести к курсора в их изменении, например, отображение окна сообщения или диалоговое окно, вызовите [восстановить](#restore) функции-члена для восстановления курсор ожидания. Допустимо вызывать **восстановить** даже когда курсор ожидания в настоящее время отображается.  
  
 Другой способ отображения курсора ожидания является использование сочетание [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)и, возможно, [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Однако `CWaitCursor` проще в использовании, так как не требуется установить курсор на предыдущем курсор после завершения работы с длительной операции.  
  
> [!NOTE]
>  MFC задает и восстанавливает курсора с помощью [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) виртуальной функции. Можно переопределить эту функцию, чтобы обеспечить пользовательское поведение.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CWaitCursor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Для отображения курсора ожидания, просто объявите `CWaitCursor` объекта до его код, который выполняет длительных операций.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор автоматически вынуждает курсор ожидания для отображения.  
  
 Когда объект выходит за пределы области (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор к предыдущей курсора. Другими словами объект выполняет необходимые очистки автоматически.  
  
 Можно воспользоваться преимуществами тот факт, что деструктор вызывается в конце блока (это может быть до окончания функции) чтобы сделать активной курсор ожидания в части функции. Этот способ показан в приведенном ниже втором примере.  
  
> [!NOTE]
>  Из-за их конструкторы и деструкторы работе `CWaitCursor` объекты всегда объявляются как локальные переменные, они никогда не описаны как глобальные переменные, а также их выделения с **новый**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 Чтобы восстановить курсор ожидания, эта функция вызывается после выполнения операции, например, отображение окна сообщения или диалоговое окно «», которые могут быть изменены курсор ожидания для другого курсора.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Примечания  
 Может вызвать **восстановить** даже когда курсор ожидания в настоящее время отображается.  
  
 Если вам требуется восстановить курсор ожидания, пока в функции, кроме одной, в котором `CWaitCursor` объект объявлен, вы можете вызвать [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [Как изменить курсор мыши в приложении классов Microsoft Foundation I:](http://go.microsoft.com/fwlink/linkid=128044)



