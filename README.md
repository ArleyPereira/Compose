# Utilização do Compose

A partir da versão 'V-2401.1.1' (branch develop), ficou disponível a utilização do Compose no App.

Algumas observações a serem seguidas na utilização do Compose:

1. Sempre utilizar o Compose em novas funcionalidades.
2. Utilizar o XML em fluxos atualmente em XML ou discutir em equipe a utilização do Compose em fluxos existentes em XML.
3. Para cada nova funcionalidade, deve-se criar um módulo (Android Library) com o nome da funcionalidade dentro do módulo features.

## Estrutura de Camadas

### Data
   - **api:** Interfaces com as requisições
      - AuthenticationService.kt
   - **mapper:** Mapeamento dos objetos entre as camadas 'domain' -><- 'data'
      - AuthenticationMapper.kt
   - **model:** Modelos utilizados na camada
      - **request:**
         - LoginRequest.kt
         - RegisterRequest.kt
      - **response:**
         - LoginResponse.kt
         - RegisterResponse.kt
   - **repository:** Implementação do repositório
      - AuthenticationApiDataSourceImpl.kt
      - AuthenticationLocalDataSourceImpl.kt

### Domain
   - **model:** Modelos utilizados na camada
      - Login.kt
      - Register.kt
   - **repository:** Interface do repositório
      - AuthenticationApiDataSource.kt
      - AuthenticationLocalDataSource.kt
   - **usecase:** Casos de uso
      - LoginUseCase.kt
      - RegisterUseCase.kt

### Presenter
   - **activity:** Activity responsável pela funcionalidade
      - AuthenticationActivity.kt
   - **graphs:** Gráficos pertencentes à funcionalidade
      - RootNavGraph.kt
      - AuthenticationNavGraph.kt
   - **routes:** Rotas pertencentes à funcionalidade
      - GraphRoutes.kt
      - AuthenticationRoutes.kt
   - **screen:** Telas pertencentes à funcionalidade
      - LoginScreen.kt
      - RegisterScreen.kt
      - RecoverScreen.kt
   - **components:** Componentes específicos da funcionalidade
      - TextField.kt
      - Button.kt

## Estrutura para Telas em Compose

### Login (Nome do Pacote)
   - **action:** Ações do usuário em tela
      - LoginAction.kt
   - **parameter:** Parâmetros caso a tela receba
      - LoginParameter.kt
   - **state:** Estados da tela
      - LoginState.kt
   - **view:** Tela
      - LoginScreen.kt
   - **viewmodel:** ViewModel
      - LoginViewModel.kt
