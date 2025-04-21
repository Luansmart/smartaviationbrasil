# Documentação da Loja Virtual SMART AVIATION

## Visão Geral

Esta documentação fornece instruções detalhadas sobre como utilizar e manter a loja virtual da SMART AVIATION, uma plataforma especializada em ferramentas aeronáuticas para oficinas, mecânicos e proprietários de aeronaves.

O sistema foi desenvolvido utilizando Next.js, React, TypeScript e Tailwind CSS, oferecendo uma interface moderna, responsiva e alinhada com a identidade visual da SMART AVIATION.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

- `/src/app`: Páginas principais da aplicação
- `/src/components`: Componentes reutilizáveis
- `/src/types`: Definições de tipos TypeScript
- `/public`: Arquivos estáticos (imagens, ícones)
- `/data`: Armazenamento de dados (produtos em JSON)

## Acesso ao Painel Administrativo

Para acessar o painel administrativo:

1. Navegue até `/admin/login` na URL do seu site
2. Use as seguintes credenciais:
   - Usuário: `admin`
   - Senha: `smartaviation`

**Importante**: Em ambiente de produção, recomenda-se alterar estas credenciais para garantir a segurança do sistema.

## Gerenciamento de Produtos

### Visualizar Produtos

1. Faça login no painel administrativo
2. Clique em "Produtos" no menu lateral
3. Você verá uma lista de todos os produtos cadastrados

### Adicionar Novo Produto

1. No painel administrativo, vá para "Produtos"
2. Clique no botão "Adicionar Produto"
3. Preencha o formulário com as informações do produto:
   - **Informações Básicas**: Nome, preço, categoria, descrição
   - **Especificações Técnicas**: Adicione características e valores
   - **Compatibilidade**: Indique com quais aeronaves o produto é compatível
   - **Certificações**: Adicione certificações como ANAC, FAA, etc.
4. Clique em "Criar Produto" para salvar

### Editar Produto Existente

1. No painel administrativo, vá para "Produtos"
2. Localize o produto que deseja editar
3. Clique no botão "Editar"
4. Atualize as informações necessárias
5. Clique em "Atualizar Produto" para salvar as alterações

### Excluir Produto

1. No painel administrativo, vá para "Produtos"
2. Localize o produto que deseja excluir
3. Clique no botão "Excluir"
4. Confirme a exclusão quando solicitado

## Gerenciamento de Imagens

### Adicionar Imagens de Produtos

1. Faça upload das imagens para a pasta `/public/images/products/`
2. Ao cadastrar ou editar um produto, use o caminho `/images/products/nome-da-imagem.jpg` no campo "URL da Imagem"

### Substituir a Logo

1. Prepare a nova imagem de logo
2. Substitua o arquivo em `/public/images/logo.jpg`
3. Mantenha o mesmo nome de arquivo para garantir que todas as referências continuem funcionando

## Personalização do Site

### Cores e Estilo

As cores principais do site estão definidas em `/src/app/globals.css` como variáveis CSS:

```css
:root {
  --smart-blue: #1e3c72;
  --smart-green: #00a651;
  --smart-yellow: #ffc20e;
  --smart-light-blue: #8dd8f8;
  --smart-purple: #2e2a5a;
  --smart-red: #c1272d;
  --smart-brown: #8c7c6d;
  /* outras variáveis */
}
```

Para alterar o esquema de cores, modifique estes valores mantendo os nomes das variáveis.

### Componentes Principais

- **Header**: `/src/components/Header.tsx` - Cabeçalho com logo e menu
- **Footer**: `/src/components/Footer.tsx` - Rodapé com informações de contato
- **ProductCard**: `/src/components/ProductCard.tsx` - Card para exibição de produtos

## Estrutura de Dados

### Modelo de Produto

Os produtos seguem esta estrutura:

```typescript
interface Product {
  id: string;
  name: string;
  description: string;
  longDescription?: string;
  price?: number;
  category: string;
  subcategory?: string;
  imageUrl: string;
  gallery?: string[];
  specifications?: Record<string, string>;
  compatibility?: string[];
  certifications?: string[];
  manual?: string;
  datasheet?: string;
  featured?: boolean;
  inStock?: boolean;
}
```

### Armazenamento de Dados

Os produtos são armazenados em `/data/products.json`. Este arquivo é gerenciado automaticamente pela API quando você usa o painel administrativo.

## API

O sistema inclui uma API RESTful para gerenciamento de produtos:

- `GET /api/products` - Lista todos os produtos
- `POST /api/products` - Adiciona um novo produto
- `GET /api/products/[id]` - Obtém um produto específico
- `PUT /api/products/[id]` - Atualiza um produto existente
- `DELETE /api/products/[id]` - Remove um produto

## Manutenção e Atualizações

### Backup de Dados

Recomenda-se fazer backup regular do arquivo `/data/products.json` para evitar perda de dados.

### Atualizações do Sistema

Para atualizar o sistema:

1. Faça backup dos dados e arquivos personalizados
2. Aplique as atualizações no código-fonte
3. Teste as alterações em ambiente de desenvolvimento
4. Implante as atualizações no ambiente de produção

## Solução de Problemas

### Produto não aparece no site

- Verifique se o produto foi cadastrado corretamente no painel administrativo
- Confirme se a categoria está correta
- Verifique se a URL da imagem está correta e se a imagem existe

### Erro ao fazer login no painel administrativo

- Verifique se está usando as credenciais corretas
- Limpe os cookies do navegador e tente novamente
- Se o problema persistir, verifique os logs do servidor

### Imagens não aparecem

- Confirme se as imagens foram carregadas para o diretório correto
- Verifique se os caminhos das imagens estão corretos nos produtos
- Certifique-se de que os formatos de imagem são suportados (JPG, PNG, WebP)

## Suporte

Para suporte técnico ou dúvidas sobre o sistema, entre em contato com a equipe de desenvolvimento.

---

Documentação preparada para SMART AVIATION - Ferramentas Aeronáuticas
