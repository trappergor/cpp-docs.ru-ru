---
title: 'Практическое: Создание и использование экземпляров weak_ptr | Документация Майкрософт'
ms.custom: how-to
ms.date: 07/12/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73b70a68226be14b7e99afe125b3dcd8b6784601
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034820"
---
# <a name="how-to-create-and-use-weakptr-instances"></a>Практическое руководство. Создание и использование экземпляров weak_ptr
Иногда объект должен хранить способ доступа к базовым объектом объекта `shared_ptr` не вызывая счетчик ссылок увеличивается. Как правило, такая ситуация возникает при наличии циклических ссылок между `shared_ptr` экземпляров.  

 Рекомендации к разработке — избегать совместного владения указателей при любой возможности. Тем не менее если необходимо иметь общее владение `shared_ptr` экземпляров, избегайте цикличных связей между ними. При цикловой ссылки неизбежны или даже предпочтительны по некоторым причинам, использовать `weak_ptr` для одного или нескольких владельцев слабую ссылку на другой `shared_ptr`. С помощью `weak_ptr`, можно создать `shared_ptr` , присоединяется к существующему набору связанных экземпляров, но только если базовый ресурс памяти по-прежнему допустим. Объект `weak_ptr` сам не участвует в подсчете ссылок, и таким образом, ничто не препятствует счетчик ссылок нулевое. Тем не менее, можно использовать `weak_ptr` для получения новой копии `shared_ptr` с которым она была инициализирована. Если память уже была удалена, `bad_weak_ptr` возникает исключение. Если эта память по-прежнему действительна, новый общий указатель увеличивает счетчик ссылок и гарантирует, что память будет допустима, пока `shared_ptr` переменная остается в области.  

## <a name="example"></a>Пример  
 В следующем примере кода показан случай где `weak_ptr` используется, чтобы обеспечить правильное удаление объектов, которые содержат циклические зависимости. Изучая пример, предположим, что он был создан только в том случае, после рассмотрения альтернативных решений. `Controller` Объекты представляют собой определенный аспект процесса компьютера, и они работают независимо друг от друга. Каждый контроллер должен иметь возможность запрашивать состояние других контроллеров в любое время, и каждый из них содержит частный `vector<weak_ptr<Controller>>` для этой цели. Каждый вектор содержит циклическую ссылку и, следовательно, `weak_ptr` экземпляры используются вместо `shared_ptr`.  

 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  

```Output  
Creating Controller0  
Creating Controller1  
Creating Controller2  
Creating Controller3  
Creating Controller4  
push_back to v[0]: 1  
push_back to v[0]: 2  
push_back to v[0]: 3  
push_back to v[0]: 4  
push_back to v[1]: 0  
push_back to v[1]: 2  
push_back to v[1]: 3  
push_back to v[1]: 4  
push_back to v[2]: 0  
push_back to v[2]: 1  
push_back to v[2]: 3  
push_back to v[2]: 4  
push_back to v[3]: 0  
push_back to v[3]: 1  
push_back to v[3]: 2  
push_back to v[3]: 4  
push_back to v[4]: 0  
push_back to v[4]: 1  
push_back to v[4]: 2  
push_back to v[4]: 3
use_count = 1  
Status of 1 = On  
Status of 2 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 2 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 1 = On  
Status of 3 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = O  
nStatus of 1 = On  
Status of 2 = On  
Status of 4 = On  
use_count = 1  
Status of 0 = On  
Status of 1 = On  
Status of 2 = On  
Status of 3 = On  
Destroying Controller0  
Destroying Controller1  
Destroying Controller2  
Destroying Controller3  
Destroying Controller4  
Press any key  
```  

 В качестве эксперимента измените вектор `others` быть `vector<shared_ptr<Controller>>`, а затем в выходных данных Обратите внимание, что не вызываются деструкторы при `TestRun` возвращает.  

## <a name="see-also"></a>См. также  
 [Интеллектуальные указатели](../cpp/smart-pointers-modern-cpp.md)