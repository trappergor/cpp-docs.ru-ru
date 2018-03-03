---
title: "Два способа создать объект CArchive | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1db549544d421600ed6dae1a8a987006c2ab6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="two-ways-to-create-a-carchive-object"></a>Два способа создать объект CArchive
Существует два способа создания `CArchive` объекта:  
  
-   [Неявное создание объекта CArchive через платформу](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [Явное создание объектов CArchive](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Неявное создание объекта CArchive через платформу  
 Наиболее распространенный и простой, проще создавать платформа `CArchive` объекта документа лица сохранить, сохранить как и откройте команды в меню «файл».  
  
 Вот, что платформа делает когда пользователь приложение выдает «Сохранить как» из меню «файл».  
  
1.  Представляет **Сохранить как** диалоговое окно и возвращает имя файла от пользователя.  
  
2.  Открывает файл с именем пользователем как `CFile` объект.  
  
3.  Создает `CArchive` объект, указывающий на это `CFile` объекта. При создании `CArchive` объекта платформа режиму «store» (записи, сериализации), в отличие от «загрузки» (чтение, выполнить десериализацию).  
  
4.  Вызовы `Serialize` функции, определенной в вашей **CDocument**-производного класса, передавая ему ссылку на `CArchive` объекта.  
  
 В документе `Serialize` функция затем записывает данные в `CArchive` объекта, как описано в ближайшее время. После возврата из вашего `Serialize` функции, платформа уничтожает `CArchive` объекта и затем `CFile` объекта.  
  
 Таким образом Если платформа создания `CArchive` объекта документа, необходимо сделать реализуют документа `Serialize` функции, записи и чтения в и из архива. Необходимо также реализовать `Serialize` для любого `CObject`-производных объектов, документ `Serialize` функция в свою очередь выполняет сериализацию прямо или косвенно.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a>Явное создание объектов CArchive  
 Помимо сериализации документа через платформу, существуют другие случаи, когда может потребоваться `CArchive` объекта. Например, может потребоваться выполнить сериализацию данных в и из буфера обмена, представленный `CSharedFile` объекта. Или можно использовать пользовательский интерфейс для сохранения файла, который отличается от того, предоставляемых средой. В этом случае можно явно создавать `CArchive` объекта. Это делается так же, как платформа делает, используя следующую процедуру.  
  
#### <a name="to-explicitly-create-a-carchive-object"></a>Чтобы явно создать объект CArchive  
  
1.  Создать `CFile` объекта или объекта, производного от `CFile`.  
  
2.  Передайте `CFile` в конструктор для `CArchive`, как показано в следующем примере:  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     Второй аргумент `CArchive` конструктор является перечисляемое значение, указывающее, будет ли использован для сохранения или загрузки данных в и из файла архива. `Serialize` Функция объекта проверяет это состояние, вызвав `IsStoring` функцию для объекта архива.  
  
 Когда вы закончите, сохранения или загрузки данных из `CArchive` объекта, закройте его. Несмотря на то что `CArchive` (и `CFile`) объекты будут автоматически закрывать архива (и файл), рекомендуется явным образом сделать это, поскольку он упрощает восстановление после ошибки. Дополнительные сведения об обработке ошибок см. в статье [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
#### <a name="to-close-the-carchive-object"></a>Закрытие объектов CArchive  
  
1.  В следующем примере показано, как закрыть `CArchive` объекта:  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

