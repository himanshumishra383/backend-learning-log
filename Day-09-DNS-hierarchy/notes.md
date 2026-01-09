## DNS Hierarchy (Step-by-step)

1. Client asks resolver for `www.example.com`
2. Resolver asks Root Server:
   → "Where is `.com`?"
3. Root replies with TLD name servers
4. Resolver asks TLD Server:
   → "Who handles `example.com`?"
5. TLD replies with Authoritative name servers
6. Resolver asks Authoritative Server:
   → "What is the IP?"
7. Authoritative replies:
   → `93.184.216.34`
8. Resolver caches the result (TTL) and returns IP to client

---

## Important Concepts
- Resolver does **recursive** work
- DNS servers give **iterative** replies
- Servers never chase answers
- Delegation keeps DNS scalable

---

## Mental Model
- Root → CEO (knows departments)
- TLD → Department Head (knows teams)
- Authoritative → Team Lead (knows actual data)

---

## Backend Relevance
- DNS latency debugging
- Load balancer & service discovery
- Microservices communication
- Production incident analysis

✔ Completed