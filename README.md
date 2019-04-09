# bloom-filter
Implementation of bloom filter
http://codekata.com/kata/kata05-bloom-filters/

This implementation of bloom filter allows user to specify the estimated number of entries in the bloom filter along with the false positive rate which can be tolerated.

The bloom filter would ensure that it would return true if an element has been added to the filter. However, in the case there is a chance that the bloom filter does not have the element present there is a chance that the bloom filter would return true. 

The implementation can take any type of object and create a filter. The Driver program has an example of how we can create a bloom filter which accepts elements of type string.

We determine bloom filter's bit set size and hash functions according to http://en.wikipedia.org/wiki/File:Bloom_filter_fp_probability.svg for the formula. This allows us flexibility in terms of the number of elements the bloom filter can support while giving the expected false positive rate.

In this implementation, we take the hash function and generate k hash values for the element by generating a hash with ith salt. This is deviating from the suggestion at http://codekata.com/kata/kata05-bloom-filters/ because we can guarantee fewer collisions by this technique. We have made a tradeoff of computing the hash value k times so that we have fewer collisions.

The implementation assumes a default hash function of md5 but users can opt to use an alternative hash function.

Code Coverage Report:
* BloomFilter	100% (1/1)	77% (7/9)	76% (40/52)
* BloomFilterDriver	0% (0/1)	0% (0/2)	0% (0/36)
* HashFunctionUtility	100% (1/1)	71% (5/7)	77% (24/31)
* IBloomFilter	100% (1/1)	100% (0/0)	100% (1/1)


References:
* https://blog.medium.com/what-are-bloom-filters-1ec2a50c68ff
* https://google.github.io/guava/releases/22.0/api/docs/com/google/common/hash/BloomFilter.html
* http://llimllib.github.io/bloomfilter-tutorial/
* https://hackernoon.com/probabilistic-data-structures-bloom-filter-5374112a7832

