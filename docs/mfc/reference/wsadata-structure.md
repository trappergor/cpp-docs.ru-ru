---
title: "Структура WSADATA | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WSADATA
dev_langs: C++
helpviewer_keywords: WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24cfbeb0e917914881587cb70fd345a903a08ecc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wsadata-structure"></a>Структура WSADATA
`WSADATA` Структура используется для хранения сведений о инициализации Windows Sockets, возвращенный вызовом к `AfxSocketInit` глобальной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct WSAData {  
    WORD wVersion;  
    WORD wHighVersion;  
    char szDescription[WSADESCRIPTION_LEN+1];  
    char szSystemStatus[WSASYSSTATUS_LEN+1];  
    unsigned short iMaxSockets;  
    unsigned short iMaxUdpDg;  
    char FAR* lpVendorInfo;  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 *wVersion*  
 Версия спецификации Windows Sockets, что библиотека DLL Windows Sockets ожидает, что вызывающий объект мог использовать.  
  
 *wHighVersion*  
 Самую новую версию спецификации Windows Sockets, поддерживающий эту библиотеку DLL (также закодированный как описано выше). Как правило, это то же самое, как **wVersion**.  
  
 *szDescription*  
 Нули ASCII строка, в который Windows Sockets DLL копирует описание реализация Windows Sockets, включая идентификатор поставщика. Текст (до 256 символов) может содержать любые символы, но являются cautioned поставщиков для включения элемента управления и форматирование символов: скорее всего, приложение будет помещен это для обычно используется для отображения (возможно, обрезанное) в сообщение о состоянии.  
  
 *szSystemStatus*  
 Нули ASCII строка, в который Windows Sockets DLL копирует соответствующих сведений о конфигурации и состоянии. Библиотека DLL Windows Sockets следует использовать это поле только в том случае, если сведения могут пригодиться для пользователя или технический персонал; не должен рассматриваться как расширение **szDescription** поля.  
  
 *iMaxSockets*  
 Максимальное число процессоров, которые один процесс потенциально может открыть. Реализация Windows Sockets может предоставить глобальный пул памяти для выделения к любому процессу; Кроме того его можно распределить ресурсы на уровне процесса для сокетов. Число также может отражать способом, в котором был настроен Windows Sockets DLL или сетевое программное обеспечение. Авторы приложений можно использовать это число как грубый сведения о том, является ли реализация Windows Sockets может использоваться приложением. Например, может проверять X Windows server **iMaxSockets** при первом запуске: если меньше 8, приложение отобразит сообщение об ошибке требованием для изменения конфигурации сетевого программного обеспечения. (Это ситуация, в которой **szSystemStatus** можно использовать текст.) Очевидно, что нет гарантии, конкретного приложения, фактически можно выделить **iMaxSockets** сокеты, поскольку могут быть другие приложения используют Windows Sockets.  
  
 *iMaxUdpDg*  
 Размер в байтах самой крупной датаграммы протокола UDP (User Datagram), отправленных или полученных приложения Windows Sockets. Если реализация не предусмотрено ограничение, **iMaxUdpDg** равно нулю. Во многих системах сокетов Беркли отсутствует неявное ограничение 8 192 байт на UDP-датаграммы (который фрагментированной при необходимости). Реализация Windows Sockets можно наложить ограничение, например, на основе выделения фрагмента накладные буферов. Минимальное значение **iMaxUdpDg** для совместимых Windows Sockets реализации — 512. Обратите внимание, что независимо от значения **iMaxUdpDg**, он не задействуются попытка отправить датаграмму широковещательной рассылки, большего, чем максимальный (MTU) для сети. (Windows Sockets API не предоставляет механизм для обнаружения наибольший размер MTU, но он должен быть не менее 512 байт).  
  
 *lpVendorInfo*  
 Дальний указатель на структуру данных, зависящего от поставщика. Определение этой структуры (Если указано) выходит за рамки спецификации Windows Sockets.  
  
> [!NOTE]
>  В MFC `WSADATA` структура возвращается `AfxSocketInit` функции, которая вызывается в вашей `InitInstance` функции. Можно извлекать структуры и сохранить ее в программе, если необходимо использовать данные из него позднее.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winsock2.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

