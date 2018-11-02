---
title: Класс CSocketFile
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: f31bbda1bb6428b6bcca25d6eddce98156fac1d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588842"
---
# <a name="csocketfile-class"></a>Класс CSocketFile

Объект `CFile` , используемый для отправки и получения сведений по сети с помощью Windows Sockets.

## <a name="syntax"></a>Синтаксис

```
class CSocketFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|Создает объект `CSocketFile`.|

## <a name="remarks"></a>Примечания

Вы можете подключить `CSocketFile` объект `CSocket` объекта для этой цели. Также можно и обычно присоединение `CSocketFile` объект `CArchive` упрощают отправку и получение данных с помощью MFC сериализации объекта.

Для сериализации данных (send), его вставке в архив, который вызывает `CSocketFile` функции-члены для записи данных `CSocket` объекта. Для десериализации (получение), можно извлекать данные из архива. В результате архива для вызова `CSocketFile` функции-члены для чтения данных из `CSocket` объекта.

> [!TIP]
>  Помимо использования `CSocketFile` как описано здесь, можно использовать его в виде отдельного файла объекта, так же, как с помощью `CFile`, его базового класса. Можно также использовать `CSocketFile` с любой функции сериализации MFC на основе архива. Так как `CSocketFile` не поддерживает все `CFile`сериализации функциональные возможности, некоторые MFC по умолчанию функции не совместимы с `CSocketFile`. Это особенно верно для `CEditView` класса. Не следует пытаться сериализации `CEditView` данных с помощью `CArchive` объект присоединен к `CSocketFile` с помощью `CEditView::SerializeRaw`; используйте `CEditView::Serialize` вместо этого. `SerializeRaw` Функция ожидает, что файл, который имеют функции, такие как `Seek`, в котором `CSocketFile` не поддерживает.

При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, где `CSocket::Receive` входит в цикл (с `PumpMessages(FD_READ)`) ожидание запрашиваемое количество байтов. Это Windows sockets допускает только один вызов recv одного уведомления FD_READ, но `CSocketFile` и `CSocket` разрешить несколько вызовов получаемого сообщения в FD_READ. Если вы получаете FD_READ при отсутствии данных для чтения, приложение перестает отвечать на запросы. Если вы никогда не получить другой FD_READ, приложение перестает взаимодействуют через сокет.

Эту проблему можно решить следующим образом. В `OnReceive` метод класса socket, вызов `CAsyncSocket::IOCtl(FIONREAD, ...)` перед вызовом метода `Serialize` метод класса сообщения при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных среды сети обычно менее 1096 байт). Если размер доступных данных меньше, чем требуется, дождитесь все данные будут приниматься и только после запуска операции чтения.

В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получить. Предполагается, что она объявлена в другом месте в коде.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Дополнительные сведения см. в разделе [Windows Sockets в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), а также [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxsock.h

##  <a name="csocketfile"></a>  CSocketFile::CSocketFile

Создает объект `CSocketFile`.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Параметры

*pSocket*<br/>
Сокет для присоединения к `CSocketFile` объекта.

*bArchiveCompatible*<br/>
Указывает, является ли объект файла для использования с `CArchive` объекта. Передайте значение FALSE, только в том случае, если вы хотите использовать `CSocketFile` объект как изолированное средство, как это делается изолированного `CFile` объекта, с некоторыми ограничениями. Этот флаг изменяется как `CArchive` объект присоединен к `CSocketFile` управляет свой буфер для чтения.

### <a name="remarks"></a>Примечания

Деструктор объекта разрыве сам объект сокета когда объект выходит за пределы области или удаляется.

> [!NOTE]
>  Объект `CSocketFile` можно также использовать как файл (ограниченная) без `CArchive` объекта. По умолчанию `CSocketFile` конструктора *bArchiveCompatible* параметр имеет значение TRUE. Это указывает, что объект файла для использования с архивом. Чтобы использовать объект файла без архив, передайте значение FALSE в *bArchiveCompatible* параметра.

В режиме «архив compatible» `CSocketFile` объект обеспечивает более высокую производительность и уменьшает риск «взаимоблокировка». Взаимоблокировка возникает, когда ожидающие отправки и получения сокеты друг от друга или для общего ресурса. Это может произойти, если `CArchive` объект работали с `CSocketFile` так, как с помощью `CFile` объекта. С помощью `CFile`, архива можно предположить, что при получении меньшее число байтов, чем она запрошена, конец файла был достигнут.

С помощью `CSocketFile`, тем не менее, данные сообщение в зависимости; буфер может содержать несколько сообщений, поэтому получение меньше количества запрошенных байтов не подразумевает, что конец файла. Приложение не будет блокировать в данном случае, как это может быть с `CFile`, и может продолжить чтение сообщений из буфера, пока буфер пуст. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) функция может быть полезна для мониторинга состояния буфера архива в этом случае.

Дополнительные сведения об использовании `CSocketFile`, см. в статьях [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows Sockets: пример из сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>См. также

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)
