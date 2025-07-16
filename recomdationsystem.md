# type os recomdation system 


## 1) 📊 Collaborative Filtering

Collaborative Filtering is based on **user behavior** — how users interact with items — without considering the actual content or attributes of the items.

for examples

    user and (item like dislike interaction data)
    
    user and (item rating  data)

    user and (iterm views/click data)

    user and (  item purcashe history data) 


note it does't talk about item content or attribute like , who is selling this , color or product , who is creator like that 



It assumes:  
> “Users who interacted similarly in the past will behave similarly in the future.

- Rows = Users, Columns = Items, Values = Interactions




### 🔧 Data Schemas in Collaborative Filtering

#### 📌 1. User-Item Rating (Explicit Feedback)

| User ID | Item A Rating | Item B Rating | Item C Rating | Item D Rating |
|--------|----------------|----------------|----------------|----------------|
| User1  | 5              | 3              | 4              | 1              |
| User2  | 4              | 5              | 2              | *(empty)*      |
| User3  | *(empty)*      | 4              | 5              | 3              |

- **Type:** Explicit Feedback  
- **Description:** Users explicitly rate items (1–5 stars, 1–10 scale, etc.)
- **Use Case:** Movie ratings, product reviews, course scores

---

#### 📌 2. User Likes/Dislikes (Binary)

| User ID | Item A | Item B | Item C | Item D |
|--------|--------|--------|--------|--------|
| User1  | 1 (Like) | 0 (Dislike) | 1 (Like) | 0 (Dislike) |
| User2  | 1        | 1        | 0        | 1        |

- **Type:** Explicit Feedback  
- **Description:** Binary like/dislike system (1 = liked, 0 = disliked)
- **Use Case:** YouTube thumbs up/down, Tinder swipe

---

#### 📌 3. User Clicks / Views (Implicit Feedback)

| User ID | Item A Clicked | Item B Clicked | Item C Clicked |
|--------|------------------|------------------|------------------|
| User1  | 1                | 0                | 1                |
| User2  | 0                | 1                | 1                |

- **Type:** Implicit Feedback  
- **Description:** User clicked or viewed the item, without rating it
- **Use Case:** E-commerce views, article reads

---

#### 📌 4. Purchase History

| User ID | Item A Purchased | Item B Purchased | Item C Purchased |
|--------|-------------------|-------------------|-------------------|
| User1  | 2 times           | 0                 | 5 times           |
| User2  | 0                 | 1 time            | 0                 |

- **Type:** Implicit Feedback  
- **Description:** How many times a user purchased an item
- **Use Case:** Amazon orders, grocery app purchases

---


---

## 📦 Content-Based Filtering

Content-Based Filtering relies on the **features of items** and the **user’s preferences for those features**.


It assumes:  
> “If a user liked items with certain attributes, they’ll like new items with similar attributes.”

- Doesn’t rely on other users’ opinions
- Common algorithms: **Cosine Similarity**, **TF-IDF**, **Neural Embeddings**



---

### 🔧 Data Schemas in Content-Based Filtering

#### 📌 1. Item-Feature Matrix

| Item     | is_Action | is_Comedy | is_Drama | has_Actor_X | has_Director_Y |
|----------|-----------|-----------|----------|-------------|----------------|
| Movie A  | 1         | 0         | 0        | 1           | 0              |
| Movie B  | 0         | 1         | 0        | 0           | 1              |
| Movie C  | 1         | 0         | 1        | 1           | 0              |

- **Type:** Item Metadata
- **Description:** Each item is broken down into features (binary, categorical, numerical, or text)
- **Use Case:** Movie genres, product color/brand, article keywords

---

#### 📌 2. User Profile (Derived from Likes)

| User ID | likes_Action | likes_Comedy | likes_Drama | likes_Actor_X | likes_Director_Y |
|---------|---------------|---------------|--------------|----------------|------------------|
| User1   | 2             | 0             | 1            | 2              | 0                |

- **Type:** Derived Profile  
- **Description:** Computed from items a user previously liked  
- **Use Case:** Personalized feature vector to match future items

---

#### 📌 3. Text-Based Features (e.g., Product Descriptions)

Raw text like:



Converted using techniques like:
- **TF-IDF Vectors**
- **Word Embeddings (e.g., Word2Vec, BERT)**
- **Bag-of-Words**

Used to compare item descriptions and match to user preferences.


## ⚖️ Comparison Table

| Feature                        | Collaborative Filtering             | Content-Based Filtering           |
|-------------------------------|-------------------------------------|-----------------------------------|
| Main Data Used                | User-Item Interactions              | Item Features (Metadata)          |
| Needs Other Users?            | ✅ Yes                              | ❌ No                              |
| Cold Start Problem             | New users/items = problem           | New users = problem               |
| Personalization               | ✅ Yes                              | ✅ Yes                            |
| Learns User Preferences       | From other users                    | From own history                  |
| Example Data                  | Ratings, likes, purchases           | Genre, brand, keywords            |

---

## 3) Hybrid (mix )

# 4) knowlode based filtering


         This type of recommendation system uses explicit knowledge or rules about the domain and the user’s needs or preferences to recommend items that satisfy certain criteria or constraints. It does not rely on ratings or feedback from other users, but rather on the user’s input or query. For example, if user A wants to buy a laptop with certain specifications and budget, then the algorithm may recommend a laptop that satisfies those criteria. Knowledge-based recommender systems work well when there is no or little rating history available, or when the items are complex and customizable.