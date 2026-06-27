# AI ՖՏ օգնական · Գործուղումների կարգ

Dark-theme վեբ-չաթբոթ՝ KanonX-ի ոճով, որը պատասխանում է հարցերին
ՀՀ ԿԲ «Գործուղումների կազմակերպման և գործուղման ծախսերի հատուցման կարգ»
փաստաթղթի հիման վրա, citation card-երով (հղում դեպի կոնկրետ բաժին)։

## Ֆայլեր
- `index.html` — ինտերֆեյսը (dark theme, citation card-եր, suggested հարցեր)
- `api/chat.js` — սերվերային ֈունկցիան, որը կապ է հաստատում Anthropic-ի հետ
  և անվտանգ կերպով պահում է API key-ը

## Տեղադրման քայլեր (Vercel, անվճար hosting)

### 1. Ստացեք Anthropic API key
1. Բացեք https://console.anthropic.com
2. Ստեղծեք հաշիվ (եթե դեռ չունեք)
3. Գնացեք "API Keys" բաժինը և ստեղծեք նոր key (սկսվում է `sk-ant-`-ով)
4. "Billing" բաժնում ավելացրեք վճարման մեթոդ
5. Պահեք key-ը անվտանգ տեղում

### 2. Վերբեռնեք կոդը GitHub-ում
1. Բացեք https://github.com և ստեղծեք հաշիվ, եթե դեռ չունեք
2. Սեղմեք "New repository", տվեք անուն (օրինակ՝ `ai-ft-ognakan`)
3. Բացեք նոր repository-ն և սեղմեք "uploading an existing file"
4. Քաշեք (drag and drop) այս փաթեթի բոլոր ֈայլերը՝ պահելով structure-ը
   (`index.html` և `api/chat.js`)
5. Սեղմեք "Commit changes"

### 3. Միացրեք Vercel-ին
1. Բացեք https://vercel.com և գրանցվեք GitHub հաշվով
2. Սեղմեք "Add New" → "Project"
3. Ընտրեք ստեղծած repository-ն ("Import")
4. "Environment Variables" բաժնում ավելացրեք.
   - Key: `ANTHROPIC_API_KEY`
   - Value: ձեր API key-ը
5. Սեղմեք "Deploy"

Մի քանի վայրկյան հետո Vercel-ը կտա URL (օրինակ՝ `ai-ft-ognakan.vercel.app`),
որը կարող եք կիսել բոլոր աշխատակիցների հետ։ Ոչ ոք պետք չէ login անի,
բացում են հասցեն ուղղակի բրաուզերում։

## Ինչպես աշխատում են citation card-երը
Claude-ը պատասխանում է հարցին, և երբ հղում է անում կարգի կոնկրետ բաժնին,
ավտոմատ ավելացնում է առանձին card՝ բաժնի անունով և ճշգրիտ մեջբերումով։
Սա կարգավորված է `api/chat.js`-ի system prompt-ի մեջ։

## Կարևոր նշումներ
- API key-ը երբեք չի երևում front-end կոդում
- Փաստաթղթի տեքստը փոփոխելու համար խմբագրեք `api/chat.js`-ի սկզբում
  գտնվող system prompt-ի փոփոխականը
- Հոստինգը (Vercel) անվճար է, Anthropic API-ի օգտագործումը՝ վճարովի ըստ ծավալի
