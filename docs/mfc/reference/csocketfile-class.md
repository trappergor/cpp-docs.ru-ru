---
title: "Класс CSocketFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- networks [C++], archive
- serialization [C++], network
- networks [C++], serializing to
- CSocketFile class
- archives [C++], network
- SOCKET handle
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6ca331c07e0a9fc48f152042fcccd5c38e743ccf
ms.lasthandoff: 02/24/2017

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
 Можно присоединить `CSocketFile` объект `CSocket` объект для этой цели. Также можно и обычно присоединение `CSocketFile` объект `CArchive` упрощают отправку и получение данных с помощью MFC сериализации объекта.  
  
 Для сериализации данных (send), его вставке в архив, который вызывает `CSocketFile` функции-члены для записи данных в `CSocket` объекта. Для десериализации (получения) данных, извлеките из архива. В результате архив для вызова `CSocketFile` функции-члены для чтения данных из `CSocket` объекта.  
  
> [!TIP]
>  Помимо использования `CSocketFile` как описано здесь, можно использовать его как объект автономного файла так же, как с `CFile`, его базового класса. Можно также использовать `CSocketFile` с сериализации функции, на основе архива MFC. Поскольку `CSocketFile` поддерживают не все `CFile`функции, по умолчанию MFC сериализации функции не совместимы с `CSocketFile`. Это особенно верно для `CEditView` класса. Не следует пытаться сериализации `CEditView` данные с помощью `CArchive` объект присоединяется к `CSocketFile` с помощью `CEditView::SerializeRaw`; используйте **CEditView::Serialize** вместо. `SerializeRaw` Функция ожидает, что файл объекта есть функции, такие как `Seek`, `CSocketFile` не имеет.  
  
 При использовании `CArchive` с `CSocketFile` и `CSocket`, может возникнуть ситуация, когда **CSocket::Receive** входит в цикл (по **PumpMessages(FD_READ)**) ожидает запрошенное количество байтов. Это, поскольку Windows sockets допускает только один вызов recv FD_READ уведомления, но `CSocketFile` и `CSocket` разрешить несколько вызовов recv на FD_READ. Если вы получите FD_READ, когда нет данных для чтения, приложение зависает. Если вы никогда не получить другой FD_READ, приложение перестает взаимодействуют через сокет.  
  
 Эту проблему можно устранить следующим образом. В `OnReceive` метод класса socket, вызов **CAsyncSocket::IOCtl (FIONREAD,...) ** перед вызовом метода `Serialize` метод класса сообщения при ожидаемые данные для считывания из сокета превышает размер одного пакета TCP (наибольший размер передаваемых данных среднего сети, обычно менее 1096 байт). Если объем доступных данных меньше, чем требуется, дождаться получения данных для получения и только затем запустить операцию чтения.  
  
 В следующем примере `m_dwExpected` приблизительное число байтов, которые пользователь ожидает получения. Предполагается, что он объявляется в другом месте в коде.  
  
 [!code-cpp[NVC_MFCSocketThread&#4;](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
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
 Указывает, является ли объект файла для использования с `CArchive` объекта. Передайте **FALSE** только в том случае, если вы хотите использовать `CSocketFile` объекта в автономном режиме как автономный `CFile` объекта, с некоторыми ограничениями. Этот флаг изменяется как `CArchive` объект присоединяется к `CSocketFile` управляет его буфер для чтения.  
  
### <a name="remarks"></a>Примечания  
 Деструктор объекта разрыве связи сам объект сокета когда объект выходит за пределы области или удаляется.  
  
> [!NOTE]
>  Объект `CSocketFile` может также использоваться как файл (ограниченная) без `CArchive` объекта. По умолчанию `CSocketFile` конструктора `bArchiveCompatible` параметр **TRUE**. Это указывает, что объект файла для использования с архивом. Чтобы использовать объект файла без архив, передайте **FALSE** в `bArchiveCompatible` параметр.  
  
 В режиме «архив совместимый» `CSocketFile` объект обеспечивает более высокую производительность и уменьшает опасность «взаимоблокировке». Взаимоблокировка возникает, когда отправляющий и принимающий сокеты ожидают друг от друга или для общих ресурсов. Это может произойти, если `CArchive` объекта работал с `CSocketFile` так, как и с `CFile` объекта. С `CFile`, архив, можно предположить, что при получении меньше байтов, чем она запрошена, конец файла был достигнут.  
  
 С `CSocketFile`тем не менее, данные на основе сообщений; буфер может содержать несколько сообщений, поэтому получение меньше, чем количество запрошенных байтов не означает конец файла. Приложения не блокируют в данном случае, что он может с `CFile`, и он может продолжить чтение из буфера сообщений, пока буфер пуст. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) функция полезна для отслеживания состояния буфера архива в таком случае.  
  
 Дополнительные сведения по использованию `CSocketFile`, см. в статьях [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md) и [Windows Sockets: пример из сокетов с использованием архивов](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-класс](../../mfc/reference/casyncsocket-class.md)   
 [CSocket-класс](../../mfc/reference/csocket-class.md)

