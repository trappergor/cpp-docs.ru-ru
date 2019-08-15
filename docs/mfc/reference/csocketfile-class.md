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
ms.openlocfilehash: 3b969f81c0c6e1868a66aeaa1c4d9339792062df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502452"
---
# <a name="csocketfile-class"></a>Класс CSocketFile

Объект `CFile` , используемый для отправки и получения сведений по сети с помощью Windows Sockets.

## <a name="syntax"></a>Синтаксис

```
class CSocketFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSocketFile:: CSocketFile](#csocketfile)|Создает объект `CSocketFile`.|

## <a name="remarks"></a>Примечания

Для этой цели можно `CSocketFile` присоединить объект `CSocket` к объекту. Вы также можете и обычно присоединить `CSocketFile` объект `CArchive` к объекту, чтобы упростить отправку и получение данных с помощью сериализации MFC.

Для сериализации (отправки) данных необходимо вставить их в архив, который вызывает `CSocketFile` функции-члены для записи данных `CSocket` в объект. Чтобы десериализовать (получить) данные, извлеките их из архива. Это приводит к тому, что `CSocketFile` Архив вызывает функции членов для считывания `CSocket` данных из объекта.

> [!TIP]
>  Помимо использования `CSocketFile` , как описано здесь, его можно использовать как отдельный файловый объект, как и в случае с `CFile`базовым классом. Можно также использовать `CSocketFile` с любыми функциями сериализации MFC на основе архива. Поскольку `CSocketFile` не поддерживает `CFile`все функции, некоторые функции сериализации MFC по умолчанию несовместимы с `CSocketFile`. Это особенно справедливо для `CEditView` класса. Не `CEditView` пытайтесь сериализовать данные `CSocketFile` `CArchive` через объект, присоединенный к объекту с помощью `CEditView::SerializeRaw`; вместо этого используйте `CEditView::Serialize` . Функция ждет, что объект File имеет функции, такие как `Seek`, у которых `CSocketFile` нет. `SerializeRaw`

`CArchive` При использовании `PumpMessages(FD_READ)`с `CSocketFile` и `CSocket`может возникнуть ситуация, когда `CSocket::Receive` вводит цикл (by) в ожидании запрошенного объема байтов. Это обусловлено тем, что сокеты Windows допускают только один вызов recv `CSocketFile` для `CSocket` каждого уведомления FD_READ, но и разрешают несколько вызовов recv per FD_READ. Если при отсутствии данных для чтения вы получаете FD_READ, приложение зависает. Если вы никогда не получаете другой FD_READ, приложение перестает взаимодействовать через сокет.

Эту проблему можно устранить следующим образом. В методе класса Socket вызовите `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` метод перед вызовом метода класса сообщений, когда ожидаемые данные, считываемые из сокета, превышают размер одного TCP-пакета (максимальная единица передачи сетевого носителя). `OnReceive` , обычно по крайней мере 1096 байт). Если размер доступных данных меньше, чем требуется, дождитесь получения всех данных и запустите операцию чтения только после этого.

В следующем примере `m_dwExpected` — это приблизительное число байтов, которое должен получить пользователь. Предполагается, что вы объявили его в любом расположении в коде.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Дополнительные сведения см. [в разделе сокеты Windows в MFC](../../mfc/windows-sockets-in-mfc.md), [сокеты Windows: Использование сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), а также [API Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кфиле](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Требования

**Заголовок:** афкссокк. h

##  <a name="csocketfile"></a>CSocketFile:: CSocketFile

Создает объект `CSocketFile`.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Параметры

*псоккет*<br/>
Сокет для присоединения к `CSocketFile` объекту.

*барчивекомпатибле*<br/>
Указывает, предназначен ли файловый объект для использования с `CArchive` объектом. Значение false следует передавать только в том случае, `CSocketFile` если вы хотите использовать объект изолированно, как и изолированный `CFile` объект, с определенными ограничениями. Этот флаг изменяет способ, `CArchive` которым объект, присоединенный к объекту, `CSocketFile` управляет его буфером для чтения.

### <a name="remarks"></a>Примечания

Деструктор объекта отменяет связь с объектом Socket, когда объект выходит из области действия или удаляется.

> [!NOTE]
>  Также можно использовать в качестве файла (с ограниченным доступом) `CArchive` без объекта. `CSocketFile` По умолчанию `CSocketFile` параметр *барчивекомпатибле* конструктора имеет значение true. Указывает, что файловый объект предназначен для использования с архивом. Чтобы использовать объект File без архива, передайте значение FALSE в параметре *барчивекомпатибле* .

В режиме `CSocketFile` «архивный» объект обеспечивает лучшую производительность и снижает опасность «взаимоблокировки». Взаимоблокировка возникает, когда оба приема сокетов ожидают друг друга или для общего ресурса. Такая ситуация может возникнуть, если `CArchive` объект работал `CSocketFile` `CFile` так же, как и объект. С `CFile`помощью архива можно предположить, что при получении меньшего количества байтов, чем запрошено, достигнут конец файла.

`CSocketFile`Тем не менее, данные основаны на сообщениях; буфер может содержать несколько сообщений, поэтому получение меньшего числа запрошенных байтов не подразумевает конца файла. Приложение не блокируется в этом случае `CFile`, как это возможно, и может продолжать чтение сообщений из буфера до тех пор, пока буфер не будет пустым. Функция [CArchive:: исбуфферемпти](../../mfc/reference/carchive-class.md#isbufferempty) полезна для наблюдения за состоянием буфера архива в таком случае.

Дополнительные сведения об использовании `CSocketFile`см. в статье [сокеты Windows: Использование сокетов с](../../mfc/windows-sockets-using-sockets-with-archives.md) архивами [и сокетами Windows. Пример сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>См. также

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)
