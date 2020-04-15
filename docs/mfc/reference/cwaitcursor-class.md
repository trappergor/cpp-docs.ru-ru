---
title: Класс CWaitCursor
ms.date: 11/04/2016
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
ms.openlocfilehash: 48ef8f9c965f54deafcc62451639f8c31021e900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373178"
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
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Строит `CWaitCursor` объект и отображает курсор ожидания.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWaitCursor::Восстановление](#restore)|Восстанавливает курсор ожидания после его изменения.|

## <a name="remarks"></a>Remarks

`CWaitCursor`не имеет базового класса.

Хорошие методы программирования Windows требуют отображения курсора ожидания всякий раз, когда вы выполняете операцию, которая занимает заметное количество времени.

Чтобы отобразить курсор ожидания, просто определите переменную перед кодом, `CWaitCursor` выполняя длительную операцию. Конструктор объекта автоматически приводит к отображению курсора ожидания.

Когда объект выходит из области (в конце блока, `CWaitCursor` в котором заявлен объект), его деструктор устанавливает курсор к предыдущему курсору. Другими словами, объект выполняет необходимую очистку автоматически.

> [!NOTE]
> Из-за того, как работают их конструкторы и деструкторов, `CWaitCursor` объекты всегда объявляются локальными переменными - они никогда не объявляются глобальными переменными и не распределяются новыми. **new**

Если вы выполняете операцию, которая может привести к изменению курсора, например отображение окна сообщения или окна диалогов, позвоните в функцию [элемента «Восстановление»,](#restore) чтобы восстановить курсора ожидания. Можно позвонить `Restore` даже при отображении курсора ожидания.

Еще один способ отображения курсора ожидания заключается в использовании комбинации [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), и, возможно, [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Тем `CWaitCursor` не менее, проще в использовании, потому что вам не нужно устанавливать курсор предыдущего курсора, когда вы закончите с длительной операцией.

> [!NOTE]
> MFC устанавливает и восстанавливает курсор с помощью виртуальной функции [CWinApp::DoWaitCursor.](../../mfc/reference/cwinapp-class.md#dowaitcursor) Вы можете переопределить эту функцию, чтобы обеспечить пользовательское поведение.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CWaitCursor`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a>CWaitCursor::CWaitCursor

Чтобы отобразить курсор ожидания, просто объявить объект перед кодом, `CWaitCursor` выполняя длительную операцию.

```
CWaitCursor();
```

### <a name="remarks"></a>Remarks

Конструктор автоматически отображает курсор ожидания.

Когда объект выходит из области (в конце блока, `CWaitCursor` в котором заявлен объект), его деструктор устанавливает курсор к предыдущему курсору. Другими словами, объект выполняет необходимую очистку автоматически.

Вы можете воспользоваться тем фактом, что деструктор вызывается в конце блока (который может быть до конца функции), чтобы сделать курсор ожидания активным только в части вашей функции. Этот метод показан во втором примере ниже.

> [!NOTE]
> Из-за того, как работают их конструкторы и деструкторов, `CWaitCursor` объекты всегда объявляются локальными переменными - они никогда не объявляются глобальными переменными, и они не распределяются с **новыми**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a>CWaitCursor::Восстановление

Чтобы восстановить курсор ожидания, вызовите эту функцию после выполнения операции, например, отображение окна сообщения или окна диалогов, которые могут изменить курсор ожидания на другой курсор.

```
void Restore();
```

### <a name="remarks"></a>Remarks

Можно вызвать `Restore` курсор ожидания.

Если вам нужно восстановить курсора ожидания в то время как `CWaitCursor` в функции, кроме той, в которой объект объявлен, вы можете вызвать [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget:BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget:ВосстановлениеWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[Как я: Изменить курсор мыши в приложении Microsoft Foundation Class](https://go.microsoft.com/fwlink/p/?linkid=128044)
