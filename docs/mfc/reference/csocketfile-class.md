---
title: "Класс CSocketFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs: C++
helpviewer_keywords: CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b08bff6bd803d1552861adc52ee08152025f9240
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csocketfile-class"></a>Класс CSocketFile
Объект `CFile` , используемый для отправки и получения сведений по сети с помощью Windows Sockets.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|Создает объект `CSocketFile`.|  
  
## <a name="remarks"></a>Примечания  
 Можно присоединить `CSocketFile` объект `CSocket` объект для этой цели. Также можно и обычно присоединить `CSocketFile` объект `CArchive` упрощают отправку и получение данных с помощью MFC сериализации объекта.  
  
 Для сериализации данных (send), можно вставить его в архив, который вызывает `CSocketFile` функции-члены для записи данных `CSocket` объекта. Для десериализации (получения) данные, которые извлечены из архива. В результате архива для вызова `CSocketFile` функции-члены для чтения данных из `CSocket` объекта.  
  
> [!TIP]
>  Помимо использования `CSocketFile` как описано здесь, можно использовать его в виде отдельного файла объекта, так же, как с `CFile`, его базовый класс. Можно также использовать `CSocketFile` с любой функции сериализации MFC на основе архива. Поскольку `CSocketFile` поддерживают не все `CFile`сериализации функциональные возможности, некоторые MFC по умолчанию функции не совместимы с `CSocketFile`. Это особенно верно для `CEditView` класса. Не рекомендуется для сериализации `CEditView` данных с помощью `CArchive` объект присоединен к `CSocketFile` с помощью `CEditView::SerializeRaw`; используйте **CEditView::Serialize** вместо него. `SerializeRaw` Функция ожидает объект файла, содержат функции, такие как `Seek`, которая `CSocketFile` отсутствует.  
  
 При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, где **CSocket::Receive** входит в цикл (по **PumpMessages(FD_READ)**) ожидания Запрошенное количество байтов. Это, поскольку Windows sockets допускает только один вызов recv одного уведомления FD_READ, но `CSocketFile` и `CSocket` разрешить несколько вызовов recv на FD_READ. При появлении FD_READ нет данных для чтения, приложение зависает. Если вы никогда не получить другой FD_READ, приложение выходит из режима взаимодействия через сокет.  
  
 Эту проблему можно разрешить следующим образом. В `OnReceive` метод класса socket, вызов **CAsyncSocket::IOCtl (FIONREAD,...)**  перед вызовом метода `Serialize` метод класса сообщений при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных средний сети, обычно менее 1096 байт). Если объем доступных данных меньше, чем требуется, дождитесь все данные будут приниматься и только затем запустить операцию чтения.  
  
 В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получения. Предполагается, что он объявляется в другом месте в коде.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Дополнительные сведения см. в разделе [сокеты Windows в MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md), а также [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsock.h  
  
##  <a name="csocketfile"></a>CSocketFile::CSocketFile  
 Создает объект `CSocketFile`.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pSocket`  
 Сокет для присоединения к `CSocketFile` объекта.  
  
 `bArchiveCompatible`  
 Указывает, является ли объект файла для использования с `CArchive` объекта. Передайте **FALSE** только в том случае, если вы хотите использовать `CSocketFile` объекта в автономном режиме, как изолированный `CFile` объекта, с некоторыми ограничениями. Этот флаг изменяется как `CArchive` объект присоединен к `CSocketFile` управляет свой буфер для чтения.  
  
### <a name="remarks"></a>Примечания  
 Деструктор объекта отсоединяет сам из сокета объекта, когда объект выходит за пределы области или удаляется.  
  
> [!NOTE]
>  Объект `CSocketFile` также может использоваться как файл (ограниченная) без `CArchive` объекта. По умолчанию `CSocketFile` конструктора `bArchiveCompatible` параметр **TRUE**. Это указывает, что объект файла для использования в архив. Чтобы использовать объект файла без архив, передайте **FALSE** в `bArchiveCompatible` параметра.  
  
 В режиме «compatible архива» `CSocketFile` объект обеспечивает более высокую производительность и уменьшает опасность «взаимоблокировка». Взаимоблокировка возникает, когда сокетам отправки и получения ожидают друг от друга или для общего ресурса. Подобная ситуация может возникнуть, если `CArchive` объекта работали с `CSocketFile` так, как и с `CFile` объекта. С `CFile`, архива можно предположить, что при получении меньше байтов, чем она запрошена, конец файла был достигнут.  
  
 С `CSocketFile`, тем не менее, данные на основе сообщений; буфер может содержать несколько сообщений, поэтому получение меньше, чем количество запрошенных байтов не означает конец файла. Приложения, не блокируют в данном случае что он может с `CFile`, и может продолжать чтение из буфера сообщений, пока буфер пуст. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) функции полезны для мониторинга состояния буфера архива в таком случае.  
  
 Дополнительные сведения об использовании `CSocketFile`, см. в статьях [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows Sockets: пример из сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [Класс CSocket](../../mfc/reference/csocket-class.md)
