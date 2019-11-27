---
title: Как создавать и использовать экземпляры weak_ptr
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
ms.openlocfilehash: 32e8d64fdb6449f1d40aec4161bfda54987ca66a
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245600"
---
# <a name="how-to-create-and-use-weak_ptr-instances"></a>Как создавать и использовать экземпляры weak_ptr

Иногда объект должен хранить способ доступа к базовому объекту [shared_ptr](../standard-library/shared-ptr-class.md) , не вызывая увеличения счетчика ссылок. Как правило, такая ситуация возникает при наличии циклических ссылок между экземплярами `shared_ptr`.

Оптимальное проектирование заключается в том, чтобы не допустить совместного владения указателями, когда это возможно. Однако, если требуется совместное владение экземплярами `shared_ptr`, следует избегать циклических ссылок между ними. Если циклические ссылки нецелесообразны или еще предпочтительнее по какой-либо причине, используйте [weak_ptr](../standard-library/weak-ptr-class.md) , чтобы предоставить одному или нескольким владельцам слабую ссылку на другой `shared_ptr`. С помощью `weak_ptr`можно создать `shared_ptr`, который присоединяется к существующему набору связанных экземпляров, но только в том случае, если ресурс базовой памяти по-прежнему является допустимым. Сам `weak_ptr` не участвует в подсчете ссылок и, следовательно, не может препятствовать переходу на нулевое значение счетчика ссылок. Однако можно использовать `weak_ptr`, чтобы попытаться получить новую копию `shared_ptr`, с которой он был инициализирован. Если память уже удалена, оператор bool `weak_ptr`возвращает `false`. Если память по-прежнему является допустимой, новый общий указатель увеличивает счетчик ссылок и гарантирует, что память будет действительной, пока переменная `shared_ptr` остается в области.

## <a name="example"></a>Пример

В следующем примере кода показан случай, когда `weak_ptr` используется для обеспечения правильного удаления объектов, имеющих циклические зависимости. При изучении примера предположим, что он был создан только после рассмотрения альтернативных решений. `Controller` объекты представляют некоторые аспекты процесса компьютера и работают независимо друг от друга. Каждый контроллер должен иметь возможность запрашивать состояние других контроллеров в любое время, и каждый из них содержит частный `vector<weak_ptr<Controller>>` для этой цели. Каждый вектор содержит циклическую ссылку, поэтому вместо `shared_ptr`используются `weak_ptr` экземпляры.

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
Status of 0 = On
Status of 1 = On
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

В качестве эксперимента измените Векторный `others`, чтобы он был `vector<shared_ptr<Controller>>`, а затем в выходных данных обратите внимание, что при возвращении `TestRun` не вызываются деструкторы.

## <a name="see-also"></a>См. также:

[Интеллектуальные указатели (современный C++)](../cpp/smart-pointers-modern-cpp.md)
