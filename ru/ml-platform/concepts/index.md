# О сервисе {{ ml-platform-name }}

{{ ml-platform-full-name }} упрощает использование среды разработки [JupyterLab](https://jupyter.org/) на вычислительных мощностях Яндекс.Облака. Это позволит вам производить сложные вычисления, например обучение нейронных сетей или анализ больших данных, используя привычный интерфейс Jupyter Notebook.

Если вы ещё не пользовались Jupyter Notebook, то попробуйте: ноутбуки удобны тем, что позволяют вам исполнять код последовательно и сразу визуализировать результаты. Ноутбуки также удобно использовать для подготовки аналитических отчетов и статей: между ячейками кода вы можете добавлять пояснения на языке [Markdown](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html).

## Преимущества сервиса {#advantages}

### Среда разработки, готовая к использованию {#ready-to-use}

Вам не надо тратить время на создание и обслуживание виртуальных машин — при создании нового [проекта](project.md), автоматически выделяется новая виртуальная машина.

{% include [include](../../_includes/ml-platform/project-opening-delay.md) %}

На виртуальной машине уже установлена среда разработки JupyterLab и пакеты для анализа данных и машинного обучения (TensorFlow, Keras, NumPy и [другие](preinstalled-packages.md)) — вы можете сразу начать их использовать. Полный список предустановленных пакетов.

Если какого-то пакета вам не хватает, вы можете [установить его](../operations/projects/install-dependencies.md) прямо из ноутбука.

### Автоматическое обслуживание {#auto-service}

Сервис автоматически остановит виртуальную машину, если вы не будете пользоваться проектом. Состояние интерпретатора сохранится, то есть все переменные и результаты вычислений не потеряются, и вы сможете продолжить работу, когда снова откроете проект.

{% include [include](../../_includes/ml-platform/saving-variables-warn.md) %}

### Управление вычислительными ресурсами {#control-computing-resources}

Для разных задач нужны разные вычислительные ресурсы. Для одних задач достаточно обычного процессора, а для других нужен графический процессор.

В {{ ml-platform-name }} есть разные [конфигурации](vm-configurations.md) виртуальной машины. По умолчанию проект запускается на виртуальной машине с минимальной конфигурацией <q>S</q> (32 ГБ RAM и 2 vCPU).

Вы можете [мигрировать на ВМ с другой конфигурацией](../operations/projects/control-compute-resources.md) в любой момент в процессе работы. Состояние интерпретатора сохранится.

Смена конфигурации позволит вам получить больше вычислительных ресурсов, когда они необходимы, и сэкономить, когда они не нужны.

{% include [include](../../_includes/ml-platform/default-vm-configuration.md) %}

### Файлы с данными доступны из любого проекта {#common-resources}

В {{ ml-platform-name }} файлы хранятся отдельно от ноутбуков. Вы можете загрузить файл с данными для анализа и использовать его в любом из проектов. Загруженные файлы появятся на вкладке **Ресурсы** и будут доступны изнутри проектов и снаружи.

Если вы измените содержимое файла, то оно изменится для всех проектов. Если вы создадите новый файл с помощью ноутбука изнутри проекта, этот файл будет доступен в остальных проектах.

### Ошибки не меняют состояние интерпретатора {#handling-errors}

Если при выполнении ячейки произошла ошибка, эта ячейка не обновит состояние интерпретатора. Это позволит вам не потерять результаты, полученные в предыдущих ячейках.

{% note important %}

Если в ячейке, где произошла ошибка, было присваивание значения переменной, то присваивание также будет отменено.

{% endnote %}

### Вы сможете поделиться вашими результатами {#share-results}

Вы можете [экспортировать ноутбук в формат HTML](../operations/projects/share.md) со всеми результатами расчетов и пояснениями к ячейкам и поделиться ссылкой на отчет в этом формате. Экспорт в других форматах сейчас недоступен.

Помимо экспорта ноутбука, вы можете записать результаты вычислений в файл. Он появится на вкладке **Ресурсы** и вы сможете [скачать](../operations/resources/download.md) файл или [поделиться ссылкой](../operations/resources/get-link.md) на него.

{% include [include](../../_includes/ml-platform/known-restrictions.md) %}

#### См. также {#see-also}

* [{#T}](../operations/index.md)
* [{#T}](limits.md)
* [{#T}](../pricing.md)