## Wprowadzenie do Docker-a

### a. Co to jest Docker?

Docker to platforma do wirtualizacji kontenerowej, która umożliwia izolację aplikacji i jej zależności w jednym lub wielu kontenerach, co zapewnia spójne i powtarzalne środowisko uruchomieniowe.

### b. Zalety stosowania Docker-a

Stosowanie Docker-a ma wiele korzyści, m.in.:

- Szybkie wdrażanie aplikacji i jej skalowanie,
- Izolacja aplikacji i jej zależności, co minimalizuje problemy związane z różnicami w środowisku uruchomieniowym,
- Możliwość łatwego przenoszenia aplikacji między różnymi środowiskami,
- Umożliwia stosowanie mikroserwisów,
- Minimalizacja zasobów potrzebnych do uruchomienia aplikacji,
- Współdzielenie zasobów między wieloma aplikacjami,
- Łatwość zarządzania wersjami aplikacji i zależnościami.

### c. Architektura Docker-a

Docker składa się z trzech podstawowych elementów:

- **Docker Engine** - serwer do zarządzania kontenerami,
- **Docker Hub** - rejestr kontenerów, w którym można przechowywać i udostępniać gotowe obrazy,
- **Docker CLI** - interfejs wiersza poleceń do zarządzania kontenerami.

Docker Engine składa się z kilku komponentów, m.in.:

- **Docker Daemon** - serwer Docker-a,
Docker Daemon to serwer Docker-a, który jest procesem działającym w tle na systemie operacyjnym hosta. Jest on odpowiedzialny za zarządzanie kontenerami, obrazami, sieciami, woluminami oraz innymi zasobami Docker-a.

Docker Daemon obsługuje komunikację między innymi elementami Docker-a, takimi jak Docker CLI i Docker API. Przetwarza również polecenia użytkownika, takie jak docker run czy docker build, aby utworzyć i zarządzać kontenerami i obrazami.

Docker Daemon działa w trybie bezpiecznym i domyślnie nasłuchuje na socketach Unix lub TCP, umożliwiając komunikację z innymi elementami Docker-a. Można również skonfigurować Docker Daemon do nasłuchiwania na specyficznych adresach IP lub portach, co umożliwia zdalne zarządzanie Docker-em.

Docker Daemon jest również w stanie uruchamiać kontenery w izolacji od hosta, zapewniając, że aplikacja wewnątrz kontenera działa dokładnie tak samo, jakby działała bezpośrednio na hoście. Ten rodzaj izolacji umożliwia wielu kontenerom korzystanie z tych samych zasobów, jednocześnie minimalizując wpływ na wydajność i stabilność hosta.

- **Docker API** - interfejs programistyczny dla aplikacji,
Docker API to interfejs programistyczny dla aplikacji, który umożliwia komunikację z Docker Daemonem. Docker API dostarcza zestaw RESTowych endpointów, które umożliwiają tworzenie, zarządzanie i monitorowanie kontenerów, obrazów, sieci i innych zasobów Docker-a.

Aplikacje mogą korzystać z Docker API do automatycznego tworzenia i usuwania kontenerów, pobierania obrazów z Docker Huba, monitorowania stanu kontenerów i wiele innych czynności. Docker API jest dostępny poprzez interfejs HTTP i może być używany w wielu językach programowania, takich jak Python, Java, Ruby, Node.js i wiele innych.

Docker API umożliwia również tworzenie niestandardowych narzędzi i integracji z innymi narzędziami deweloperskimi, takimi jak Jenkins, Travis CI czy GitLab. Zintegrowanie Docker API z narzędziami CI/CD umożliwia automatyczne wdrażanie aplikacji do kontenerów w chmurze, zapewniając łatwe i powtarzalne wdrażanie.

Docker API jest kluczowym elementem w architekturze Docker-a, umożliwiając komunikację między Docker CLI, Docker Compose i Docker Daemon.

- **Docker CLI** - klient wiersza poleceń do zarządzania kontenerami,
Docker CLI to klient wiersza poleceń, który umożliwia interakcję z Docker Daemonem za pomocą komend. Dzięki Docker CLI użytkownicy mogą łatwo tworzyć, zarządzać i monitorować kontenery, obrazy, sieci i inne zasoby Docker-a.

Docker CLI obsługuje wiele komend, takich jak docker run, docker build, docker push, docker pull i wiele innych. Komendy te pozwalają użytkownikom na wykonywanie różnych czynności związanych z Docker-em, takich jak uruchamianie kontenerów z obrazów, budowanie obrazów, publikowanie obrazów do Docker Huba i pobieranie obrazów z Docker Huba.

Docker CLI jest dostępny na wielu platformach, w tym na systemach Windows, Linux i macOS. Można go używać z interfejsem wiersza poleceń lub zintegrować z narzędziami deweloperskimi, takimi jak Visual Studio Code czy JetBrains IDEs.

Docker CLI jest jednym z kluczowych elementów w architekturze Docker-a i umożliwia interakcję z Docker-em za pomocą konsoli.


- **Docker Registry** - przechowuje i udostępnia gotowe obrazy kontenerów,
Docker Registry to system do przechowywania i udostępniania gotowych obrazów kontenerów. Docker Registry umożliwia użytkownikom przesyłanie, pobieranie i zarządzanie obrazami kontenerów z różnych źródeł.

Domyślnie Docker Registry jest hostowany na Docker Hubie, który jest publicznym rejestrze obrazów. Docker Hub zawiera setki tysięcy gotowych obrazów, które można łatwo pobrać i uruchomić na lokalnym środowisku. Docker Hub umożliwia również użytkownikom tworzenie i publikowanie własnych obrazów.

Istnieją jednak również prywatne rejestry Docker-a, które można hostować na własnych serwerach. Takie rejestry zapewniają prywatność i bezpieczeństwo, ponieważ użytkownicy mają pełną kontrolę nad obrazami i ich udostępnianiem. Prywatne rejestry Docker-a można łatwo skonfigurować i dostosować do indywidualnych potrzeb.

Docker Registry jest kluczowym elementem w architekturze Docker-a, umożliwiając przechowywanie i udostępnianie gotowych obrazów kontenerów dla użytkowników Docker-a.

- **Docker Compose** - narzędzie do zarządzania wieloma kontenerami jednocześnie.
Docker Compose to narzędzie do zarządzania wieloma kontenerami Docker-a jednocześnie, które umożliwia łatwe uruchamianie aplikacji składającej się z wielu usług. Docker Compose pozwala użytkownikom na definiowanie i uruchamianie aplikacji wielokontenerowych w prosty i powtarzalny sposób.

Docker Compose używa plików konfiguracyjnych YAML do definiowania usług i ich konfiguracji. W pliku Docker Compose YAML użytkownicy mogą zdefiniować wszystkie wymagane usługi, takie jak bazy danych, serwery HTTP, aplikacje klienckie i wiele innych. Docker Compose pozwala również na definiowanie zależności między usługami, takimi jak kolejność uruchamiania i czekanie na dostępność innych usług.

Docker Compose jest szczególnie przydatny podczas wdrażania i testowania aplikacji, ponieważ umożliwia użytkownikom łatwe i powtarzalne tworzenie środowisk deweloperskich i testowych. Dzięki Docker Compose można szybko utworzyć i uruchomić wielokontenerowe środowiska, co minimalizuje problemy związane z różnicami między środowiskami.

Docker Compose jest również używany w środowiskach produkcyjnych, aby łatwo zarządzać i skalować aplikacje wielokontenerowe. Docker Compose pozwala na łatwe skalowanie usług w pionie i w poziomie, zapewniając elastyczność i wydajność w środowiskach produkcyjnych.

Docker Compose jest kluczowym elementem w architekturze Docker-a, umożliwiając łatwe i powtarzalne zarządzanie wieloma kontenerami jednocześnie.

Kontenery Docker-a są tworzone z obrazów, które są zbudowane na podstawie plików konfiguracyjnych zwanych Dockerfile. Konfiguracja kontenera jest przechowywana w pliku zwany Docker Compose YAML.