---
title: "Как: Создание и использование экземпляров weak_ptr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a1ca125f72815a16c2b6ba74da35fa56b9bd066c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-and-use-weakptr-instances"></a>Практическое руководство. Создание и использование экземпляров weak_ptr
Иногда объект необходимо сохранить возможность доступа к базовым объектом для `shared_ptr` не вызывая счетчик ссылок увеличивается. Как правило, такая ситуация возникает при наличии циклических ссылок между `shared_ptr` экземпляров.  
  
 Всего состоит в том, чтобы избежать общее владение указателей, при любой возможности. Тем не менее если необходимо совместно владения `shared_ptr` экземпляров, избегайте циклических ссылок между ними. Если циклических ссылок неизбежные или даже более предпочтительным, чем для какой-либо причине, используйте `weak_ptr` для предоставления одного или нескольких владельцев слабую ссылку на другой `shared_ptr`. С помощью `weak_ptr`, можно создать `shared_ptr` , который включается в существующий набор связанных экземпляров, но только если основной ресурс памяти по-прежнему действителен. Объект `weak_ptr` сам не участвует в подсчете ссылок, и таким образом, он не могут помешать счетчик ссылок будет ноль. Тем не менее, можно использовать `weak_ptr` для получения новой копии `shared_ptr` с которой он был инициализирован. Если память уже был удален, **bad_weak_ptr** исключения. Если объем памяти по-прежнему действительна, новый общий указатель увеличивает счетчик ссылок и гарантирует, что память будет действовать, пока `shared_ptr` переменной остается в области видимости.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан случай где `weak_ptr` используется для обеспечения правильного удаления объектов, которые содержат циклические зависимости. При проверке пример, предположим, что он был создан только после рассматривались альтернативных решений. `Controller` Объекты представляют некоторые аспекты процесса машины, и они работают независимо друг от друга. Каждый контроллер должен уметь запросить состояние другие контроллеры в любое время, и каждый из них содержит закрытый `vector<weak_ptr<Controller>>` для этой цели. Каждый вектор содержит циклическую ссылку и, следовательно, `weak_ptr` экземпляры используются вместо `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
```Output  
Creating Controller0Creating Controller1Creating Controller2Creating Controller3Creating Controller4push_back to v[0]: 1push_back to v[0]: 2push_back to v[0]: 3push_back to v[0]: 4push_back to v[1]: 0push_back to v[1]: 2push_back to v[1]: 3push_back to v[1]: 4push_back to v[2]: 0push_back to v[2]: 1push_back to v[2]: 3push_back to v[2]: 4push_back to v[3]: 0push_back to v[3]: 1push_back to v[3]: 2push_back to v[3]: 4push_back to v[4]: 0push_back to v[4]: 1push_back to v[4]: 2push_back to v[4]: 3use_count = 1Status of 1 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 3 = OnDestroying Controller0Destroying Controller1Destroying Controller2Destroying Controller3Destroying Controller4Press any key  
```  
  
 В качестве эксперимента изменить вектор `others` быть `vector<shared_ptr<Controller>>`и затем в выходных данных, обратите внимание, что деструктор вызывается при `TestRun` возвращает.  
  
## <a name="see-also"></a>См. также  
 [Интеллектуальные указатели](../cpp/smart-pointers-modern-cpp.md)