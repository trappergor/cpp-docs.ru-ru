---
title: Класс CSemaphore
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 6c518b6a9ad0fe857b0878bcecd3020ba97174e6
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504715"
---
# <a name="csemaphore-class"></a>Класс CSemaphore

Объект класса `CSemaphore` представляет «семафор» — объект синхронизации, позволяющий ограниченному числу потоков в один или несколько процессах осуществлять доступ к сохраняет количество потоков, осуществляющих текущий доступ к указанным ресурсом.

## <a name="syntax"></a>Синтаксис

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|Создает объект `CSemaphore`.|

## <a name="remarks"></a>Примечания

Семафоры полезны в управлении доступом к общему ресурсу, который поддерживает только ограниченное число пользователей. Текущее количество `CSemaphore` объект — это число дополнительных пользователей, которым разрешено. Когда счетчик достигает нуля, все попытки использовать ресурс, который управляет `CSemaphore` объект будет вставлен в системной очереди и подождите, пока они либо время ожидания, или число больше 0. Максимальное число пользователей, которым разрешен доступ к управляемой ресурса за один раз указывается во время создания `CSemaphore` объекта.

Чтобы использовать `CSemaphore` объекта, создания `CSemaphore` объекта при необходимости. Укажите имя для ожидания семафора, и приложение должно изначально он принадлежит. При возврате в конструктор, можно затем получить семафора. Вызовите [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) после получения доступа к управляемой ресурсу.

Альтернативный метод с помощью `CSemaphore` объектов заключается в добавлении переменной типа `CSemaphore` как элемент данных, к классу, для управления. Во время создания управляемого объекта, вызовите конструктор `CSemaphore` элемент данных, указав начальный доступа count, счетчик максимального доступа, имя семафора (если он будет использоваться через границы процесса) и необходимости атрибуты безопасности.

Для доступа к ресурсам, которые управляются `CSemaphore` объектов таким образом, сначала создайте переменную типа [CSingleLock](../../mfc/reference/csinglelock-class.md) или тип [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции-члене доступ к ресурсу. Затем вызовите объект блокировки `Lock` функции-члена (например, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). На этом этапе поток будет либо получить доступ к ресурсу, подождите, пока ресурс освобождается и получить доступ или ожидания ресурса, освобождения и время ожидания, не удалось получить доступ к ресурсу. В любом случае ресурс уже был осуществлен потокобезопасным способом. Для освобождения ресурса, используйте объект блокировки `Unlock` функции-члена (например, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), или разрешить объект блокировки само выходит из области.

Кроме того, можно создать `CSemaphore` объекта автономного и доступ к ней явным образом перед попыткой доступа к управляемой ресурсов. Этот метод при яснее кому-либо чтение исходный код, вероятность возникновения ошибок.

Дополнительные сведения об использовании `CSemaphore` объектов, см. в статье [Многопоточность: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Требования

**Заголовок:** afxmt.h

##  <a name="csemaphore"></a>  CSemaphore::CSemaphore

Создает именованную или неименованную `CSemaphore` объекта.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Параметры

*lInitialCount*<br/>
Счетчик начальной использования семафора. Должно быть больше или равно 0 и меньше или равно *lMaxCount*.

*lMaxCount*<br/>
Максимальная загруженность семафора. Должно быть больше 0.

*pstrName*<br/>
Имя семафора. Необходимо указать, если семафора будет осуществляться через границы процессов. Если `NULL`, объект будет без имени. Если имя соответствует существующей semaphore, конструктор создает новый `CSemaphore` объект, который ссылается на семафоре этим именем. Если имя совпадает с существующий объект синхронизации, не семафор, построение завершится ошибкой.

*lpsaAttributes*<br/>
Атрибуты безопасности для объекта семафора. Полное описание этой структуры, см. в разделе [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Для доступа к или выпуска `CSemaphore` следует создать [CMultiLock](../../mfc/reference/cmultilock-class.md) или [CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены.

> [!IMPORTANT]
>  После создания `CSemaphore` , используйте [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) чтобы убедиться, что мьютекс не существовал. Если мьютексом существовала неожиданно, это может указывать нелегальные процессы — занятие и может вы собираетесь использовать мьютекс злоумышленником. В этом случае соображениям безопасности рекомендуется закрыть дескриптор и продолжить как, если произошел сбой при создании объекта.

## <a name="see-also"></a>См. также

[Класс CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
