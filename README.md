**Cast:**

* Novus, a curious apprentice learning the ways of the network.
* Pikaro the Clean, a monk of the Temple of Systems, known for his clarity and reverence for simplicity.

**Scene:**
A shaded corner of the Terminal Garden. Novus sits cross-legged before an open scroll of Go code. Pikaro approaches, sipping from a mug labeled `nil`.

---

**Novus:**
Pikaro, I found [this script](https://pkg.go.dev/net/http#example-Get) in the archives. It speaks to distant servers and fetches sacred texts. But I do not understand its structure. Will you read it with me?

**Pikaro (nodding):**
Of course, child. Let us examine it line by line, as the compiler does.

**Novus (reading):**

```go
res, err := http.Get("http://www.google.com/robots.txt")
```

**Pikaro:**
A bold beginning. This line invokes the web itself. The monk who wrote this calls upon the standard library’s `http.Get`, a method to retrieve scrolls from remote hosts. The URL, `"http://www.google.com/robots.txt"`, is the address of the scroll.

**Novus:**
I’ve heard of this *robots.txt*. Why seek it?

**Pikaro:**
It is a declaration of boundaries — a text that instructs automated agents where they may and may not tread. A kind of etiquette for digital visitors.

**Novus:**
And the `res` and `err`?

**Pikaro:**
The two truths of any network call: the response, and the possibility of failure. In Go, we are always mindful of both.

**Novus (continuing):**

```go
if err != nil {
	log.Fatal(err)
}
```

**Pikaro:**
Wise. The code halts immediately if the network failed. There is no meaning in proceeding without a scroll to read.

**Novus:**

```go
body, err := io.ReadAll(res.Body)
res.Body.Close()
```

**Pikaro:**
Here the scroll is unfurled — its full contents read into `body`. And then, importantly, the reader closes the scroll. We must not leave open connections lying around, lest they poison our future with leaks and slowness.

**Novus:**
Even if the scroll turns out to be useless?

**Pikaro:**
Even then. Discipline demands we clean up after every ritual.

**Novus (squinting):**

```go
if res.StatusCode > 299 {
	log.Fatalf("Response failed with status code: %d and\nbody: %s\n", res.StatusCode, body)
}
```

**Pikaro:**
Ah, this is a guardian of expectations. Any status code greater than 299 signals an error. This monk not only halts the program, but records the failure and its contents for the annals.

**Novus (quietly):**
Another check this?

```go
if err != nil {
	log.Fatal(err)
}
```

**Pikaro:**
Indeed. Even reading the scroll may fail — perhaps it was damaged in transit. We check again. Go teaches vigilance.

**Novus (finishing):**

```go
fmt.Printf("%s", body)
```

**Pikaro (smiling):**
And here the scroll is shared. Its text printed plainly to the standard output — humble, silent, enduring. No ceremony, just truth.

**Novus:**
So this script reaches across the net, retrieves a scroll, ensures it is valid, and shows it?

**Pikaro:**
Yes. But more than that — it teaches you the sacred loop of I/O in Go:

1. Request with care.
2. Check for failure.
3. Clean up no matter what.
4. Only trust a result if all steps succeeded.

**Novus (bowing):**
Thank you, master. I will write my next script with this ritual in mind.

**Pikaro the Clean:**
Then you have already taken the first step toward clarity.
