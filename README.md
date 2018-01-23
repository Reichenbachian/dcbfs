# Decentralized Cloud-Based File Storage

This is a system where files are encrypted and uploaded in pieces to a decentralized hive of internet-connected machines, where they are accessible at any time from any other machine that has the correct encryption key.

Each file will have to have a unique identifier, which will be a combination of the publisher's username and the filename. Each filename will be associated with a ledger which describes where each chunk of it is stored, since it will most likely have many copies of each chunk stored across multiple machines.

To upload a file, it will be encrypted with the key associated with the publisher, and then split into several chunks. A header will be attached to each chunk containing some kind of hash of the file name. Then each chunk will be copied to several machines in the hive that have set aside space to store files in exchange for uploading their own files. (The tradeoff is storage space for accessibility across machines.) A ledger will be created that records where each piece of the file is stored. Another part of the process will be that computers periodically review each file's ledger to check that several copies of each chunk are available, and create more copies of a chunk and then update the ledger if necessary. Each individual ledger could possibly be blockchain-based. To delete a file, the original publisher will release a revocation statement (similar to revoking a pubkey?) and the chunks will gradually be deleted. Every time a computer verifies the integrity of a file by checking for the chunks, it leaves a timestamp on the chunk to say so. If a chunk is not verified for a long period of time, it can be deleted (this ensures that dead chunks aren't left over if the ledger is deleted).