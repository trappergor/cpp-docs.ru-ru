---
title: Класс CWaitCursor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4867b98a9778c818ab19d5325782b24e29282fca
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077989"
---
# <a name="cwaitcursor-class"></a>Класс CWaitCursor

Предоставляет односторонний способ отображения курсора ожидания (который обычно отображается как песочные часы) при выполнении длительной операции.

## <a name="syntax"></a>Синтаксис

```
class CWaitCursor
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Создает `CWaitCursor` и отображает курсор ожидания.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWaitCursor::Restore](#restore)|Восстанавливает курсор ожидания после он изменяется.|

## <a name="remarks"></a>Примечания

`CWaitCursor` не имеет базового класса.

Хороший Windows, программирования требуют отображения курсора ожидания при каждом выполнении операции, которая занимает много времени.

Чтобы отобразить курсор ожидания, просто определите `CWaitCursor` переменной перед кодом, который выполняет длительной операции. Конструктор объекта автоматически вынуждает курсор ожидания для отображения.

Когда объект выходит за пределы области действия (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор до предыдущей позиции курсора. Другими словами объект выполняет необходимые очистки автоматически.

> [!NOTE]
>  Из-за их конструкторы и деструкторы работы `CWaitCursor` объекты всегда объявляются как локальные переменные, они никогда не объявляются как глобальные переменные, ни их выделения с **новый**.

При выполнении операции, что может привести к курсор для изменения, такие как отображение окна сообщения или диалоговое окно, вызов [восстановить](#restore) функция-член для восстановления курсор ожидания. Допустимо вызывать `Restore` даже когда курсор ожидания отображается в текущий момент.

Другой способ отображения курсора ожидания является использование сочетания [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)и, возможно, [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Тем не менее `CWaitCursor` проще в использовании, поскольку вы не установите курсор в предыдущем курсор, когда все будет готово длительной операции.

> [!NOTE]
>  MFC задает и восстанавливает курсора с помощью [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) виртуальной функции. Можно переопределить эту функцию, чтобы обеспечить пользовательское поведение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CWaitCursor`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

##  <a name="cwaitcursor"></a>  CWaitCursor::CWaitCursor

Чтобы отобразить курсор ожидания, просто объявите `CWaitCursor` объекта перед кодом, который выполняет длительной операции.

```
CWaitCursor();
```

### <a name="remarks"></a>Примечания

Конструктор автоматически вынуждает курсор ожидания для отображения.

Когда объект выходит за пределы области действия (в конце блока, в котором `CWaitCursor` объявлен объект), его деструктор задает курсор до предыдущей позиции курсора. Другими словами объект выполняет необходимые очистки автоматически.

Можно воспользоваться преимуществами тот факт, что деструктор вызывается в конце блока (что может быть до окончания функции) курсор ожидания active только часть вашей функции. Во втором примере ниже показан этот метод.

> [!NOTE]
>  Из-за их конструкторы и деструкторы работы `CWaitCursor` объекты всегда объявляются как локальные переменные, они никогда не объявляются как глобальные переменные, а также их выделения с **новый**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

##  <a name="restore"></a>  CWaitCursor::Restore

Чтобы восстановить курсор ожидания, эта функция вызывается после выполнения операции, такие как отображение окна сообщения или диалоговое окно, которое может изменить курсор ожидания для другого курсора.

```
void Restore();
```

### <a name="remarks"></a>Примечания

Это нормально для вызова `Restore` даже когда курсор ожидания отображается в текущий момент.

Если необходимо восстановить курсор ожидания в функции, кроме того, в котором `CWaitCursor` объявлен объект, вы можете вызвать [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[Как изменить курсор мыши на приложение классов Microsoft Foundation I:](http://go.microsoft.com/fwlink/p/?linkid=128044)

