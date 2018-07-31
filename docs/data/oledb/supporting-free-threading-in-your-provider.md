---
title: Поддержка свободной потоковой модели в поставщике | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 17750a61675f9b208be69b86ec7b044b6b19f1bb
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336681"
---
# <a name="supporting-free-threading-in-your-provider"></a>Поддержка свободной потоковой модели в поставщике
Все классы поставщика OLE DB являются поточно ориентированными и записи реестра заданы соответствующим образом. Рекомендуется Поддержка свободной потоковой модели помогают обеспечить высокий уровень производительности в многопользовательских ситуациях. Для обеспечения актуальности поставщику поточно ориентированными, необходимо убедиться, что ваш код заблокирован должным образом. Каждый раз, когда записи или хранения данных, необходимо заблокировать доступ с помощью критических секций.  
  
 Каждый объект шаблона поставщика OLE DB имеет свой собственный критический раздел. Блокирование, каждый новый создаваемый класс должен быть класс шаблона, принимающий родительского класса имя в качестве аргумента.  
  
 В следующем примере показано, как блока кода:  
  
```cpp  
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
  
 Дополнительные сведения о том, как защитить критические секции с `Lock` и `Unlock`, см. в разделе [Многопоточность: Практическое использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Также необходимо убедиться, что все методы можно переопределять (такие как `Execute`) являются поточно ориентированными.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)