---
title: "Поддержка свободной потоковой модели в поставщике | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 14bd61bc4f319a50abdbf76d7f6e60e511e57312
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-free-threading-in-your-provider"></a>Поддержка свободной потоковой модели в поставщике
Все классы поставщика OLE DB являются потокобезопасными, и соответствующим образом устанавливаются параметры реестра. Рекомендуется Поддержка свободной потоковой модели для обеспечения высокого уровня производительности в многопользовательских ситуациях. Чтобы сохранить поточно-поставщиком, необходимо проверить код заблокирован соответствующим образом. Каждый раз, когда записи или хранения данных, необходимо заблокировать доступ к критическим секциям.  
  
 Каждый объект шаблона поставщика OLE DB имеет собственную критическую секцию. Чтобы облегчить блокирование, каждый новый создаваемый класс необходимо класс шаблона, принимающий родительский класс в качестве аргумента имя.  
  
 В следующем примере показано, как блок кода:  
  
```  
template <class T>  
class CMyObject<T> : public...  
  
HRESULT MyObject::MyMethod(void)  
{  
   T* pT = (T*)this;      // this gets the parent class   
  
// You don't need to do anything if you are only reading information  
  
// If you want to write information, do the following:  
   pT->Lock();         // engages critical section in the object  
   ...;                // write whatever information you wish  
   pT->Unlock();       // disengages the critical section  
}  
```  
  
 Дополнительные сведения о том, как защитить критические секции с `Lock` и `Unlock`, в разделе [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Также необходимо убедиться, что любые методы можно переопределить (такие как `Execute`) являются потокобезопасными.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)